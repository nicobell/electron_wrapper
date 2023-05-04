<template>
  <div class="map-wrapper" id="roro_connections_line">
    <svg version="1.1" 
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1920 1080" 
        :class="this.zoomlevel">
      
      <g class="linea" id="linea_1">
        <path class="st1" d="m1011.75,569.28l-14.66,14.64h-17.23l-5.9-5.9v-27.74l-33.92-33.92,2.01-2.01" />
      </g>
      <g class="punto" id="punto_1">
        <circle class="st2" cx="1011.75" cy="569.22" r="3.3" />
        <circle class="st3" cx="1011.75" cy="569.22" r=".8" />
      </g>

      <g class="linea" id="linea_2">
        <path class="st1" d="m1007.78,573.17l.03-12.59,10.87-10.87h9.61" />
      </g>
      <g class="punto" id="punto_2">
        <circle class="st2" cx="1028.14" cy="549.71" r="3.3" />
        <circle class="st3" cx="1028.14" cy="549.71" r=".8" />
      </g>

      <g class="linea" id="linea_3">
        <path class="st1" d="m997.09,583.92h24.56l8.46,8.46h14.15l3.38-3.38h8.18l8.14-8.14" />
      </g>
      <g class="punto" id="punto_3">
        <circle class="st2" cx="1063.68" cy="581.09" r="3.3" />
        <circle class="st3" cx="1063.68" cy="581.09" r=".8" />
      </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap'
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
  name: 'RoRoLines',
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
    gsap.to('#roro_connections_line svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })
  
    gsap.fromTo("#roro_connections_line #linea_1 path", { drawSVG: "100% 100%" }, { duration: 2, drawSVG: "0% 100%", delay: this.d+1 });
    gsap.fromTo("#roro_connections_line #punto_1 .st2", { opacity: 0 }, { duration: 0.3,  opacity: 0.45, delay: this.d+2.5 });
    gsap.fromTo("#roro_connections_line #punto_1 .st3", { opacity: 0 }, { duration: 0.3,  opacity: 1, delay: this.d+2.5 });

    gsap.fromTo("#roro_connections_line #linea_3 path", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", delay: this.d+2 });
    gsap.fromTo("#roro_connections_line #punto_3 .st2", { opacity: 0 }, { duration: 0.3,  opacity: 0.45, delay: this.d+2.5 });
    gsap.fromTo("#roro_connections_line #punto_3 .st3", { opacity: 0 }, { duration: 0.3,  opacity: 1, delay: this.d+2.5 });

    gsap.fromTo("#roro_connections_line #linea_2 path", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", delay: this.d+2 });
    gsap.fromTo("#roro_connections_line #punto_2 .st2", { opacity: 0 }, { duration: 0.3,  opacity: 0.45, delay: this.d+2.5 });
    gsap.fromTo("#roro_connections_line #punto_2 .st3", { opacity: 0 }, { duration: 0.3,  opacity: 1, delay: this.d+2.5 });
  }
}
</script>

<style scoped>

/* linee di collegamento */
.st1 {
  stroke: #9AF2E3;
  stroke-width: 0.02vw;
}

/* areola dello spot */
.st2 {
  opacity: 0.45;
  fill: #9AF2E3;
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