<template>
  <div class="map-wrapper" id="hungary_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

    <g class="linea" id="linea_1">
      <path mask="url(#linea1_mmask)" class="medium_line_full" d="m938.88,507.44h25.51l8.92-8.92" />
      <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
        <path id="linea1_mask" class="medium_line_full" d="m938.88,507.44h25.51l8.92-8.92" />
      </mask>
    </g>
    <g class="punto" id="punto_1">
      <path class="medium_spot" d="m973.31,497.57c.43,0,.78.35.78.78s-.35.78-.78.78-.78-.35-.78-.78c0-.43.35-.78.78-.78h0Z" />
    </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Hungary',
    props: {
      zoomlevel: String,
      state: Object,
      io: String,
      d: Number
    },
    mounted() {
      gsap.registerPlugin(DrawSVGPlugin);
      gsap.to('#hungary_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#hungary_lines svg > .linea mask path", { drawSVG: "0% 0%" }, {duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d });
      gsap.from("#hungary_lines svg > .punto > *", { duration: .3,  opacity: 0, stagger: .2, delay: this.d+1 });
    }
}
</script>

<style scoped>
</style>