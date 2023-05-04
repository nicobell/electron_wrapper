<template>
  <div class="map-wrapper" id="luxemburg_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

    <g class="linea" id="linea_1">
      <path mask="url(#linea1_mmask)" class="medium_line" d="m934.13,507.97l-26.34-26.34h-8.02" />
      <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
        <path id="linea1_mask" class="medium_line" d="m934.13,507.97l-26.34-26.34h-8.02" />
      </mask>
    </g>
    <g class="punto" id="punto_1">
      <path class="medium_spot" d="m899.42,481.02c.34,0,.61.27.61.61s-.27.61-.61.61-.61-.27-.61-.61c0-.34.27-.61.61-.61h0Z" />
    </g>

    <g id="other_connections">
      <g class="linea" id="linea_2">
        <path class="other_conn_spot" d="m898.75,481.29l-2.89-2.89-12.56-12.15" />
      </g>
      <g class="punto" id="punto_2">
        <circle class="other_conn_line" cx="883.28" cy="466.25" r=".25" />
        <circle class="other_conn_inner" cx="883.28" cy="466.25" r=".2" />
      </g>
    </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Luxemburg',
    props: {
      zoomlevel: String,
      state: Object,
      io: String,
      d: Number
    },
    beforeMount() {
      gsap.registerPlugin(DrawSVGPlugin);
    },
    mounted() {
      gsap.to('#luxemburg_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#luxemburg_lines svg > .linea mask path", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d });
      gsap.from("#luxemburg_lines svg > .punto > *", { duration: .3,  opacity: 0, stagger: .2, delay: this.d+1 });

      gsap.from("#luxemburg_lines #other_connections path", { duration: 0.5,  opacity: 0, delay: this.d+1.5 });
      gsap.from("#luxemburg_lines #other_connections circle", { duration: 0.5,  opacity: 0, delay: this.d+1.5 });
    }
}
</script>

<style scoped>
</style>