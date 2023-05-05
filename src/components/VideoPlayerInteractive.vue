<template>
    <div>
        <div :class="{'pattern': !this.interactive, 'primopiano': this.interactive}" 
            id="videomain" ref="player"></div>

        <video ref="video" id="video" loop crossOrigin="anonymous" playsinline style="display:none">
			<source :src="`videos/`+this.activesrc+'.mp4'">
		</video>

        <button v-if="this.interactive" class="closevideo" @click="this.closevideo()"></button>
        <h2 v-if="this.interactive">{{ this.title }}</h2>

        <InterGorizia v-if="this.interactive && this.id=='interporto_gorizia'" @update-video-index="this.updateVideo" />
        <InterCervignano v-if="this.interactive && this.id=='interporto_cervignano'" @update-video-index="this.updateVideo"/>
        <InterPordenone v-if="this.interactive && this.id=='interporto_pordenone'" @update-video-index="this.updateVideo"/>
        <PortoMonfalcone v-if="this.interactive && this.id=='porto_monfalcone'" @update-video-index="this.updateVideo"/>
        <PortoNogaro  v-if="this.interactive && this.id=='porto_nogaro'" @update-video-index="this.updateVideo" />
        <InterFreeEste  v-if="this.interactive && this.id=='interporto_freeeste'" @update-video-index="this.updateVideo" />
        <PortoTrieste  v-if="this.interactive && this.id=='porto_trieste'" @update-video-index="this.updateVideo" />

    </div>
</template>

<script>
import * as THREE from 'three';
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';

import InterFreeEste from './maps/InterFreeEste.vue'
import InterCervignano from './maps/InterCervignano.vue'
import InterGorizia from './maps/InterGorizia.vue'
import InterPordenone from './maps/InterPordenone.vue'
import PortoMonfalcone from './maps/PortoMonfalcone.vue'
import PortoNogaro from './maps/PortoNogaro.vue'
import PortoTrieste from './maps/PortoTrieste.vue'

export default {
    name: "VideoPlayerInteractive",
    props: {
        src: Array,
        title: String,
        interactive: Boolean,
        id: String
    },
    components: {
        InterFreeEste,
        InterCervignano,
        InterGorizia,
        InterPordenone,
        PortoNogaro,
        PortoMonfalcone,
        PortoTrieste
    },
    data() {
        return {
            lat: 0,
            lon: 0,
            phi: 0,
            theta: 0,
            distance: 50,
            videoindex: 0,
            controls: null,
            animationRequestId: null,
            resetMap: ''
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
            this.animationRequestId = requestAnimationFrame(this.animate.bind(this))
            this.renderer.render(this.scene, this.camera)
        },
        createScene() {
            let width = window.innerWidth;
            let height = window.innerHeight;

            this.camera = new THREE.PerspectiveCamera(75, width / height, 1, 1100);
            this.scene = new THREE.Scene();

            const geometry = new THREE.SphereGeometry(500, 60, 40);
            geometry.scale(-1, 1, 1);

            this.$refs.video.loop = true
            this.$refs.video.crossOrigin = 'anonymous'
            this.$refs.video.currentTime = 1;
            
            this.texture = new THREE.VideoTexture(this.$refs.video);

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

            this.mesh = new THREE.Mesh(geometry, this.material);

            this.scene.add(this.mesh);

            this.renderer = new THREE.WebGLRenderer();
            this.renderer.setPixelRatio(window.devicePixelRatio);
            this.renderer.setSize(window.innerWidth, window.innerHeight);
            
            this.$refs.player.appendChild(this.renderer.domElement);

            let vs = this

            this.controls = new OrbitControls(vs.camera, vs.renderer.domElement)

            this.controls.autoRotate = false
            this.controls.enableDamping = true
            this.controls.rotateSpeed = -0.25
            this.controls.panSpeed = -0.25
            this.controls.dampingFactor = 0.1
            this.controls.maxDistance = 1000
            this.controls.minDistance = 0
            
            this.centerCamera()

            this.animate()
        },
    },
    unmounted() {
        cancelAnimationFrame(this.animationRequestId)
    },
    mounted() {
        this.createScene()
    },
    watch: {
        interactive() {
            if(this.interactive)
                this.$refs.video.play()
            else {
                this.$refs.video.pause()
                this.$refs.video.currentTime = 1
            }
        },
        activesrc() {
            this.$refs.video.load()

            cancelAnimationFrame(this.animationRequestId)
            
            this.$refs.video.play()
            
            this.centerCamera()
            this.animate()
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
    background-color: #000;
}

.pattern::after {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;
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