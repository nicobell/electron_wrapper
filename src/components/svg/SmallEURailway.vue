<template>
  <div class="map-wrapper" id="small_eu_white_line">
    <svg version="1.1" 
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1920 1080" 
        :class="this.zoomlevel">

      <g id="linee">
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_1" class="linea st1" d="m910.93,467.39v6.78l15.58,15.58v10.07l8.25,8.16" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_2" class="linea st1" d="m942.43,514.37h20.43l8.24-8.67v-5.66" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_3" class="linea st1" d="m960.92,493.01v7.53l-10.85,10.68h-11.03" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_4" class="linea st1" d="m950.49,508.29l-1.97,2.15h-9.76" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_5" class="linea st1" d="m933.19,511.11h-11.85l-21.21-21.21v-8.11" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_6" class="linea st1" d="m943.88,495.36v1.3l-4.26,4.26v5.06" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_7" class="linea st1" d="m939.56,506.79h3.3l6.71-6.61v-20.14h14.52" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="linea_8" class="linea st1" d="m923.04,520.76l5.93-6.1h4.54l3.4-3.67" />

        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_1" class="punto st3" d="m910.93,466.98c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7h0c0-.39.31-.7.7-.7Z" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_2" class="punto st3" d="m971.09,498.95c.4,0,.72.32.72.72s-.32.72-.72.72-.72-.32-.72-.72.32-.72.72-.72Z" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_3" class="punto st3" d="m961.18,492.44c.4,0,.72.32.72.72s-.32.72-.72.72-.72-.32-.72-.72.32-.72.72-.72Z" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_4" class="punto st3" d="m950.49,507.06c.4,0,.72.32.72.72s-.32.72-.72.72-.72-.32-.72-.72.32-.72.72-.72Z" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_5" class="punto st3" d="m900.15,480.46c.4,0,.72.32.72.72s-.32.72-.72.72-.72-.32-.72-.72.32-.72.72-.72Z" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_6" class="punto st3" d="m943.58,494.21c.4,0,.72.32.72.72s-.32.72-.72.72-.72-.32-.72-.72.32-.72.72-.72Z" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_7" class="punto st3" d="m964.24,479.27c.4,0,.72.32.72.72s-.32.72-.72.72-.72-.32-.72-.72.32-.72.72-.72Z" />
        <path  v-show="this.zoomlevel == 'zoom-global'" id="punto_8" class="punto st3" d="m922.74,520.04c.4,0,.72.32.72.72s-.32.72-.72.72-.72-.32-.72-.72.32-.72.72-.72Z" />
      </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'SmalEURailway',
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
      gsap.to('#small_eu_white_line svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y })

      gsap.fromTo("#small_eu_white_line .linea", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", stagger: 0.1, delay: this.d });
      gsap.from("#small_eu_white_line .punto", { duration: 0.3,  opacity: 0, delay: this.d+1 });
    },
    watch: {
      zoomlevel() {
        if(this.zoomlevel == 'zoom-global') {
          gsap.fromTo("#small_eu_white_line .linea", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", stagger: 0.1, delay: this.d });
          gsap.fromTo("#small_eu_white_line .punto", { opacity: 0 }, { duration: 0.3,  opacity: 1, delay: this.d+1 });
        }
      }
    }
}
</script>

<style scoped>

/* linee di collegamento */
.st1 {
  stroke: #fff;
  stroke-width: .02vw;
  fill: none;
}

/* cerchio bianco nello spot */
.st3 {
  stroke: #FFF;
  fill: #FFF;
  stroke-width: .1vw;
  transform-origin: center center;
  transform-box: fill-box;
  transition: transform 2000ms ease;
}

/* stile spessore stroke in base allo zoom */
.zoom-europe .st3 {
    transform: scale(.3);
    transition: transform 2000ms ease;
}

.zoom-europe .st1 {
  transition: stroke-width 2000ms ease;
  stroke-width: 0.02vw;
}


</style>