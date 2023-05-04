<template>
  <div class="map-wrapper" id="feeder_connections_line">
    <svg xmlns="http://www.w3.org/2000/svg" 
      viewBox="0 0 1920 1080"
      :class="this.zoomlevel" >

      <g class="linea" id="linea_principale">
        <path id="Tracciato_34051" class="st0" d="m939.64,512.84l-4.49,4.81,9.48,9.55" />
      </g>

      <g class="linea" id="linea_1">
        <line class="st1" x1="936.01" y1="516.16" x2="934.84" y2="514.99" />
      </g>
      <g class="punto" id="punto_1">
        <circle class="st2" cx="934.79" cy="515.05" r="1.5" />
        <circle class="st3" cx="934.79" cy="515.05" r=".4" />
      </g>

      <g class="linea" id="linea_2">
        <line class="st1" x1="937.27" y1="520.33" x2="934.75" y2="522.85" />
      </g>
      <g class="punto" id="punto_2">
        <circle class="st2" cx="934.49" cy="523.06" r="1.5" />
        <circle class="st3" cx="934.49" cy="523.06" r=".4" />
      </g>

      <g class="linea" id="linea_3">
        <line class="st1" x1="944.28" y1="527.39" x2="942.33" y2="529.33" />
      </g>
      <g class="punto" id="punto_3">
        <circle class="st2" cx="942.04" cy="529.55" r="1.5" />
        <circle class="st3" cx="942.04" cy="529.55" r=".4" />
      </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap'
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
  name: "FeederLines",
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
    gsap.to('#feeder_connections_line svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0})
  
    gsap.fromTo("#feeder_connections_line #linea_principale path", { drawSVG: "0%" }, { duration: 2, drawSVG: "100%", delay: this.d+1 });
    
    gsap.fromTo("#feeder_connections_line .linea line", { drawSVG: "0% 0%" }, { duration: 0.5, drawSVG: "0% 100%", stagger: 0.1, delay: this.d+2.5 });

    gsap.from("#feeder_connections_line .punto", { duration: 0.3,  opacity: 0, stagger: 0.1, delay: this.d+3 });
  }
};
</script>

<style scoped>

/* linee di collegamento */
.st1,
.st0 {
  stroke: #BDD61E;
  fill: none;
}

.st1 { stroke-width: 0.02vw; }
.st0 { stroke-width: 0.04vw; }

/* areola dello spot */
.st2 {
  opacity: .3;
  fill: #BDD61E;
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

</style>