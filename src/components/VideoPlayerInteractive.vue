<template>
    <div>
        <div :class="{'pattern': !this.interactive, 'primopiano': this.interactive}" 
            id="videomain" ref="player"></div>

        <video ref="video" id="video" loop muted crossOrigin="anonymous" playsinline style="display:none">
			<source :src="`videos/`+this.activesrc+'.mp4'">
		</video>

        <button v-if="this.interactive" class="closevideo" @click="this.closevideo()"></button>
        <h2 v-if="this.interactive">{{ this.title }}</h2>

        
        <InterGorizia v-if="this.interactive && this.id=='interporto_gorizia'" @update-video-index="this.updateVideo" />
        <InterCervignano v-if="this.interactive && this.id=='interporto_cervignano'" @update-video-index="this.updateVideo"/>
        <InterPordenone v-if="this.interactive && this.id=='interporto_pordenone'" @update-video-index="this.updateVideo"/>
        <PortoMonfalcone v-if="this.interactive && this.id=='porto_monfalcone'" @update-video-index="this.updateVideo"/>
        <PortoNogaro  v-if="this.interactive && this.id=='porto_nogaro'" @update-video-index="this.updateVideo" />
        <FreeEste  v-if="this.interactive && this.id=='interporto_freeeste'" @update-video-index="this.updateVideo" />
        <InterTrieste  v-if="this.interactive && this.id=='interporto_freeeste'" class="left" @update-video-index="this.updateVideo" />

    </div>
</template>

<script>
import * as THREE from 'three';
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';

import FreeEste from './maps/FreeEste.vue'
import InterCervignano from './maps/InterCervignano.vue'
import InterGorizia from './maps/InterGorizia.vue'
import InterPordenone from './maps/InterPordenone.vue'
import InterTrieste from './maps/InterTrieste.vue'
import PortoMonfalcone from './maps/PortoMonfalcone.vue'
import PortoNogaro from './maps/PortoNogaro.vue'

export default {
    name: "VideoPlayerInteractive",
    props: {
        src: Array,
        title: String,
        interactive: Boolean,
        id: String
    },
    components: {
        FreeEste,
        InterCervignano,
        InterGorizia,
        InterPordenone,
        InterTrieste,
        PortoNogaro,
        PortoMonfalcone
    },
    data() {
        return {
            lat: 0,
            lon: 0,
            phi: 0,
            theta: 0,
            distance: 50,
            videoindex: 0,
            controls: null
        }
    },
    computed: {
        activesrc() {
            return this.src[this.videoindex]
        }
    },
    methods: {
        updateVideo(id) {
            this.videoindex = id
        },
        closevideo() { 
            this.$emit('close-video')
        },
        centerCamera() {
            this.lat = Math.max(-85, Math.min(85, this.lat))
            this.phi = THREE.MathUtils.degToRad(90 - this.lat)
            this.theta = THREE.MathUtils.degToRad(this.lon)

            this.camera.position.x = this.distance * Math.sin(this.phi) * Math.cos(this.theta)
            this.camera.position.y = this.distance * Math.cos(this.phi)
            this.camera.position.z = this.distance * Math.sin(this.phi) * Math.sin(this.theta)

            this.camera.lookAt(0, 0, 0)

            this.renderer.render(this.scene, this.camera)
        },
        animate() {
            requestAnimationFrame(this.animate.bind(this))
            this.renderer.render(this.scene, this.camera)
        },
        createScene() {
            let width = window.innerWidth;
            let height = window.innerHeight;

            this.camera = new THREE.PerspectiveCamera(75, width / height, 1, 1100);
            this.scene = new THREE.Scene();

            const geometry = new THREE.SphereGeometry(500, 60, 40);
            geometry.scale(-1, 1, 1);

            this.$refs.video.muted = true
            this.$refs.video.loop = true
            this.$refs.video.crossOrigin = 'anonymous'
            this.$refs.video.play()

            this.texture = new THREE.VideoTexture(this.$refs.video);
            
            //peggiora performance ????
            //this.texture.encoding = THREE.sRGBEncoding;

            this.material = new THREE.ShaderMaterial({
                uniforms: {
                    uTexture: { value: this.texture }
                },
                vertexShader: `
                    varying vec2 vUv;

                    void main() {
                        vUv = uv;
                        gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
                    }
                `,
                fragmentShader: `
                    uniform sampler2D uTexture;
                    varying vec2 vUv;

                    void main() {
                        vec4 texelColor = texture(uTexture, vUv);
                        // sRGB to linear conversion
                        texelColor.xyz = pow(texelColor.xyz, vec3(2.2));
                        // Linear to gamma conversion
                        texelColor.xyz = pow(texelColor.xyz, vec3(1.0/2.2));
                        gl_FragColor = texelColor;
                    }
                `
            });

            //this.material = new THREE.MeshBasicMaterial({map: this.texture});
            this.mesh = new THREE.Mesh(geometry, this.material);

            this.scene.add(this.mesh);

            this.renderer = new THREE.WebGLRenderer();
            this.renderer.setPixelRatio(window.devicePixelRatio);
            this.renderer.setSize(window.innerWidth, window.innerHeight);
            
            this.$refs.player.appendChild(this.renderer.domElement);

            let vs = this

            /* let touchX, mouseX;
            this.$refs.player.addEventListener('touchstart', e => {
                touchX = e.touches[0].clientX;
            });
            this.$refs.player.addEventListener('touchmove', e => {
                let deltaX = e.touches[0].clientX - touchX;
                vs.camera.rotation.y += deltaX * 0.002;
                touchX = e.touches[0].clientX;
            });

            this.$refs.player.addEventListener('mousedown', e => {
                mouseX = e.clientX;
                this.$refs.player.addEventListener('mousemove', onMouseMove);
            });
            this.$refs.player.addEventListener('mouseup', e => {
                this.$refs.player.removeEventListener('mousemove', onMouseMove);
            });

            let onMouseMove = e => {
                let deltaX = e.clientX - mouseX;
                vs.camera.rotation.y += deltaX * 0.002;
                mouseX = e.clientX;
            }; */

            // Create a new OrbitControls object and pass in the camera and renderer
            this.controls = new OrbitControls(vs.camera, vs.renderer.domElement)

            // Disable auto rotation and enable damping
            this.controls.autoRotate = false
            this.controls.enableDamping = true

            // Set the damping factor
            this.controls.dampingFactor = 0.1

            // Set the maximum distance and minimum distance of the camera from the scene
            this.controls.maxDistance = 1000
            this.controls.minDistance = 10

            this.$refs.player.addEventListener('mousedown', () => {
                /* mouseX = e.clientX;
                mouseY = e.clientY; */
                this.$refs.player.addEventListener('mousemove', this.onDocumentMouseMove);
            });
            this.$refs.player.addEventListener('mouseup', () => {
                this.$refs.player.removeEventListener('mousemove', this.onDocumentMouseMove);
            });

            this.$refs.player.addEventListener('touchstart', () => {
            });
            this.$refs.player.addEventListener('touchmove', () => {
                this.$refs.player.removeEventListener('mousemove', this.onDocumentMouseMove);
            });

            // Add an event listener for when the mouse is moved
            //this.renderer.domElement.addEventListener('mousemove', onDocumentMouseMove, false)

            // Define the onDocumentMouseMove function

            this.centerCamera()

            this.animate()
        },
        onDocumentMouseMove(event) {
            // Calculate the mouse position relative to the canvas
            let mouseX = (event.clientX / window.innerWidth) * 2 - 1
            let mouseY = -(event.clientY / window.innerHeight) * 2 + 1

            // Set the rotation angles based on the mouse position
            let rotationX = mouseY * Math.PI / 2
            let rotationY = mouseX * Math.PI / 2

            // Create a new Quaternion object
            let quaternion = new THREE.Quaternion()

            // Calculate the rotation using the Quaternion object
            quaternion.setFromEuler(new THREE.Euler(
                THREE.MathUtils.degToRad(-rotationX * -1),
                THREE.MathUtils.degToRad(-rotationY * -1),
                0,
                'XYZ'
            ))

            // Apply the rotation to the camera
            this.camera.quaternion.copy(quaternion)

            // Update the controls
            this.controls.update()
        }
    },
    mounted() {
        this.createScene()
    },
    watch: {
        activesrc() {
            this.$refs.video.load()
            this.$refs.video.play()
            this.centerCamera()
        }
    }
}
</script>

<style scoped>

.left {
    transform: translateX(-19vw);
}

#videomain {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
    background-color: #fff;
}

.pattern::after {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;
    /* background: linear-gradient(to right, #08253d 0%, transparent 50%, #08253d 100%), url(../assets/pattern_retina.png); */
    background-image: url(../assets/sfumatura_dark_dx.png);
    background-size: contain;
    background-position: right top;
    background-repeat: no-repeat;
    opacity: .7;
    z-index: 0;
}

#videomain.primopiano {
    z-index: 100;
}

.closevideo {
    position: fixed;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    z-index: 100;
    cursor: pointer;
    width: 8vw;
    background-color: var(--main_color);
    background-image: url(../assets/close.png);
    background-size: 1.5vw 1.5vw;
    background-position: center center;
    background-repeat: no-repeat;
    height: 5vw;
    border-top-left-radius: .5vw;
    border-top-right-radius: .5vw;
    border: none;
    padding-bottom: 2vw;
}

h2 {
    font-size: 2vw;
    font-weight: 700;
    color: #fff;
    top: 2vw;
    left: 2vw;
    max-width: 25%;
    position: fixed;
    z-index: 100;
    margin: 0;
}

</style>