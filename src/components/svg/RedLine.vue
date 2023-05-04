<template>
  <div class="map-wrapper" id="big_red_line">
    <svg 
        version="1.1" 
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1920 1080" 
        :class="this.zoomlevel"
    >
        <g id="linea_lunga">
            <path id="main_tracciato" class="st1 main_tracciato" d="m1592.76,590.02v56.34l-148.49,149.28h-126.27l-60.8-60.8h-130.87l-58.85-58.85-9.71-9.93v-17.74l-5.13-12.85-9.42-11.65v-7.91l-22.33-15.16h-28.61l-20.11-20.11v-29.59l-34.73-34.73,3.27-3.27" />/>
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_1">
            <path id="Tracciato_34045" class="st1" d="m1028.65,549.58l-43.18,43.18" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_1">
            <circle class="st2" cx="1028.65" cy="549.58" r="10.3" />
            <circle class="st3" cx="1028.65" cy="549.58" r="3.08" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_2">
            <path id="Tracciato_34044" class="st1" d="m1014.18,571.36l-25.02,25.02" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_2">
            <circle class="st2" cx="1014.18" cy="570.36" r="10.3" />
            <circle class="st3" cx="1014.18" cy="570.36" r="3.08" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_3">
            <path id="Tracciato_34046" class="st1" d="m1064.21,581.87l-28.27,28.27" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_3">
            <circle class="st2" cx="1064.21" cy="581.87" r="10.3" />
            <circle class="st3" cx="1064.21" cy="581.87" r="3.08" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_4">
            <path id="Tracciato_32482" class="st1" d="m1077.39,661.55l-12.8,13.04" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_4">
            <circle class="st2" cx="1076.5" cy="661.24" r="10.3" />
            <circle class="st3" cx="1076.5" cy="661.24" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_5">
            <path id="Tracciato_32483" class="st1" d="m1085.38,676.37l-10.03,9.45" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_5">
            <circle class="st2" cx="1084.52" cy="676.62" r="10.3" />
            <circle class="st3" cx="1084.52" cy="676.62" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_6">
            <path id="Tracciato_32481" class="st1" d="m1168.32,706.65l28.17,28.13" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_6">
            <circle class="st2" cx="1167.84" cy="706.31" r="10.3" />
            <circle class="st3" cx="1167.84" cy="706.31" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_7">
            <path id="Tracciato_32480" class="cls-2" d="m1430.09,783.41l13,12.66" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_7">
            <circle class="st2" cx="1429.62" cy="782.46" r="10.3" />
            <circle class="st3" cx="1429.62" cy="782.46" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_8">
            <circle class="st2" cx="1442.91" cy="796.82" r="10.3" />
            <circle class="st3" cx="1442.91" cy="796.82" r="3.1" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_9">
            <path id="Tracciato_32479" class="st1" d="m1505.34,674.29l30.29,30.29" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_9">
            <circle class="st2" cx="1504.86" cy="673.81" r="10.3" />
            <circle class="st3" cx="1504.86" cy="673.81" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_10">
            <path id="Tracciato_32478" class="st1" d="m1542.42,633.36l31.45,31.44" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_10">
            <circle class="st2" cx="1541.94" cy="632.88" r="10.3" />
            <circle class="st3" cx="1541.94" cy="632.88" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_11">
            <path id="Tracciato_33778" class="st1" d="m1549.56,625.92l32.76,30.46" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_11">
            <circle class="st2" cx="1549.09" cy="625.64" r="10.3" />
            <circle class="st3" cx="1549.09" cy="625.64" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_12">
            <path id="Tracciato_32476" class="st1" d="m1529.89,567.92l61.85,61.97" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_12">
            <circle class="st2" cx="1529.17" cy="567.66" r="10.3" />
            <circle class="st3" cx="1529.17" cy="567.66" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="linea" id="linea_13">
            <path id="Tracciato_32475" class="st1" d="m1547.1,564.93l44.52,43.61" />
        </g>
        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_13">
            <circle class="st2" cx="1546.63" cy="564.45" r="10.3" />
            <circle class="st3" cx="1546.63" cy="564.45" r="3.1" />
        </g>

        <g v-show="this.zoomlevel=='zoom-global'" class="punto" id="punto_14">
            <circle class="st2" cx="1592.76" cy="590.24" r="10.3" />
            <circle class="st3" cx="1592.76" cy="590.24" r="3.1" />
        </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'RedLine',
    props: {
        zoomlevel: String,
        state: Object,
        d: Number,
        io: String
    },
    beforeMount() {
        gsap.registerPlugin(DrawSVGPlugin);
    },
    mounted() {
        gsap.to('#big_red_line svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

        if(this.zoomlevel=='zoom-global') {
            gsap.fromTo("#linea_lunga path",  { drawSVG: "100% 100%" }, { duration: 2, drawSVG: "0% 100%", delay: this.d });

            gsap.fromTo("#big_red_line .linea path", { drawSVG: "100% 100%" }, { duration:  0.5, drawSVG: "0% 100%", stagger: 0.1, delay: this.d+.5 });
            gsap.from("#big_red_line .punto", { duration: 0.3,  opacity: 0, stagger: 0.1, delay: this.d+.7 });

        } else {
            gsap.fromTo("#linea_lunga path",  { drawSVG: "100% 100%" }, { duration: 6, drawSVG: "0% 100%", delay: this.d });   
        }

    },
    watch: {
        zoomlevel() {
            if(this.zoomlevel == 'zoom-global') {
                gsap.fromTo("#big_red_line .linea path", { drawSVG: "100% 100%" }, { duration:  0.5, drawSVG: "0% 100%", stagger: 0.2 });
                gsap.fromTo("#big_red_line .punto", { opacity: 0 }, { duration: 0.3, opacity: 1, stagger: 0.2, delay: .3 });

            } else {
                gsap.fromTo("#big_red_line .linea path", { drawSVG: "0% 100%" }, { duration:  0.3, drawSVG: "100% 100%", stagger: 0.2 });
                gsap.fromTo("#big_red_line .punto", { opacity: 1 }, { duration: 0.3, opacity: 0, stagger: 0.2, delay: .3 });
            }
        }
    }
}
</script>

<style scoped>

/* linee di collegamento */
.st1 { stroke: #EB503F; }

/* areola dello spot */
.st2 {
    opacity: 0.45;
    fill: #EB503F;
    transform-origin: center center;
    transform-box: fill-box;
    transition: transform 2000ms ease;
}

/* cerchio bianco nello spot */
.st3 {
    fill: #FFFFFF;
    transform-origin: center center;
    transform-box: fill-box;
    transition: transform 2000ms ease;
}

/* stile spessore stroke in base allo zoom */
.zoom-country .st2,
.zoom-europe .st2,
.zoom-country .st3,
.zoom-europe .st3 {
    transform: scale(.5);
    transition: transform 2000ms ease;
}

</style>
