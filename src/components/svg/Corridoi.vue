<template>
  <div class="map-wrapper" id="corridoi">
    <svg 
        version="1.1" 
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1920 1080" 
        :class="this.zoomlevel"
    >
        <g id="corridoio_1">
            <path mask="url(#L_1_mmask)" id="linea_1" class="linea dashed orange" d="m927.68,518.47l1.49-3.43,7.35-2.26,2.48-.62,1.43.67,1.91.9.83.28,3.33-.69,8.53-1.17" />
            <mask id="L_1_mmask" maskUnits="userSpaceOnUse"> 
                <path id="L_1_mask" class="mask linea dashed orange" d="m927.68,518.47l1.49-3.43,7.35-2.26,2.48-.62,1.43.67,1.91.9.83.28,3.33-.69,8.53-1.17" />
            </mask>
            <path id="linea_2" class="linea orange" d="m927.95,518.23l1.3-3.14,7.02-2.15,2.73-.83,1.43.67,1.91.9.83.28,11.86-1.85" />
        </g>

        <g id="corridoio_2">
            <path id="linea_3" class="linea yellow" d="m920.14,514.17l3.6.92,2.57-1.09,2.87,1.01,9.97-2.94" />
            
            <path mask="url(#L_4_mmask)" id="linea_4" class="linea dashed yellow" d="m919.59,514.1l4.25,1.06,2.56-1.23,2.83,1.03,9.87-2.91" />
            <mask id="L_4_mmask" maskUnits="userSpaceOnUse"> 
                <path id="L_4_mask" class="mask linea dashed yellow" d="m919.59,514.1l4.25,1.06,2.56-1.23,2.83,1.03,9.87-2.91" />
            </mask>

            <path id="linea_5" class="linea yellow " d="m939.15,512.07l.13-1.96-.47-1.21-.22-1.12,1.27-.55.64-.73h1.37l2.11-1.65,4.59-.06,10.7-8.84" />
            
            <path  mask="url(#L_6_mmask)" id="linea_6" class="linea dashed yellow" d="m939.1,512.03l-.2-1.5-.48-1.22-.2-1.34,2.09-.53-.13-.91.56.1h.87l.2-.32,1.63-1.74,3.53-.08,7.05-8.79" />
            <mask id="L_6_mmask" maskUnits="userSpaceOnUse"> 
                <path id="L_6_mask" class="mask linea dashed yellow" d="m939.1,512.03l-.2-1.5-.48-1.22-.2-1.34,2.09-.53-.13-.91.56.1h.87l.2-.32,1.63-1.74,3.53-.08,7.05-8.79" />
            </mask>

            <path id="linea_7" class="linea yellow" d="m939.15,512.08l3.26,1.64.79.26,1.91-.31,4.74-.74,1.65.94" />
            
            <path  mask="url(#L_8_mmask)" id="linea_8" class="linea dashed yellow" d="m939.14,512.12l3.11,1.5.71.19.22.19,1.8-.39,1.45-.35,3.04-.35,2.04.07" />
            <mask id="L_8_mmask" maskUnits="userSpaceOnUse"> 
                <path id="L_8_mask" class="mask linea dashed yellow" d="m939.14,512.12l3.11,1.5.71.19.22.19,1.8-.39,1.45-.35,3.04-.35,2.04.07" />
            </mask>
        </g>

        <g id="linee_poli">
            <path mask="url(#L_9_mmask)" id="linea_9" class="dashed blue" d="m942.54,513.77l.58.96" />
            <mask id="L_9_mmask" maskUnits="userSpaceOnUse"> 
                <path id="L_9_mask" class="mask linea dashed blue" d="m942.54,513.77l.58.96" />
            </mask>

            <line  id="linea_10" class="linea blue" x1="938.21" y1="513.3" x2="939.21" y2="512.3" />
            <line  id="linea_11" class="linea blue" x1="941.07" y1="511.32" x2="939.95" y2="512.43" />
            <polyline  id="linea_12" class="linea blue" points="942.22 514.5 942.54 514.17 942.26 513.72" />
            <line  id="linea_13" class="linea blue" x1="935.67" y1="511.31" x2="936.98" y2="512.61" />
        </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Corridoi',
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
        gsap.to('#corridoi svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

        gsap.fromTo("#corridoi #L_1_mask", { drawSVG: "100% 100%" }, { duration:  2, drawSVG: "0% 100%", delay: this.d+1 });
        gsap.fromTo("#corridoi #linea_2", { drawSVG: "100% 100%" }, { duration:  2, drawSVG: "0% 100%", delay: this.d+1 });
        
        gsap.fromTo("#corridoi #linea_3", { drawSVG: "0% 0%" }, { duration:  1, drawSVG: "0% 100%", delay: this.d+1 });
        gsap.fromTo("#corridoi #L_4_mask", { drawSVG: "0% 0%" }, { duration:  1, drawSVG: "0% 100%", delay: this.d+1 });

        gsap.fromTo("#corridoi #linea_5", { drawSVG: "0% 0%" }, { duration:  2, drawSVG: "0% 100%", delay: this.d+2 });
        gsap.fromTo("#corridoi #L_6_mask", { drawSVG: "0% 0%" }, { duration:  2, drawSVG: "0% 100%", delay: this.d+2 });

        gsap.fromTo("#corridoi #linea_7", { drawSVG: "0% 0%" }, { duration:  1, drawSVG: "0% 100%", delay: this.d+2 });
        gsap.fromTo("#corridoi #L_8_mask", { drawSVG: "0% 0%" }, { duration:  1, drawSVG: "0% 100%", delay: this.d+2 });
        
        gsap.fromTo("#corridoi #linee_poli .mask", { drawSVG: "0% 0%" }, { duration:  1, drawSVG: "0% 100%", delay: this.d+2 });
        gsap.fromTo("#corridoi #linee_poli > .linea", { drawSVG: "0% 0%" }, { duration:  1, drawSVG: "0% 100%", delay: this.d+2 });
    }
}
</script>

<style scoped>


.linea {
    fill: none;
    stroke-width: .0025vw;
    isolation: isolate;
}

.dashed {
    stroke-dasharray: 0 0 .23 .04;
}

.orange {
    opacity: .7;
    stroke: #f80;
}

.yellow {
    stroke: #ffe71a;
    opacity: .7;
}

.blue {
    stroke: #6b9bd2;
}

.mask { 
    stroke: #fff; 
    opacity: 1;
}

</style>
