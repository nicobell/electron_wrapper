<template>
  <div class="map-wrapper" id="holland_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

    <g class="linea" id="linea_1">
      <path mask="url(#linea1_mmask)" class="medium_line_full" d="m889.28,461.16l47.93,47.93" />
      <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
        <path id="linea1_mask" class="medium_line_full" d="m889.28,461.16l47.93,47.93" />
      </mask>
    </g>
    <g class="punto" id="punto_1">
      <path class="medium_spot" d="m889.13,460.04c.51,0,.93.41.93.93s-.41.93-.93.93-.93-.41-.93-.93c0-.51.41-.93.93-.93h0Z" />
    </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Holland',
    props: {
      zoomlevel: String,
      state: Object,
      io: String,
      d: Number
    },
    mounted() {
      gsap.registerPlugin(DrawSVGPlugin);
      gsap.to('#holland_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#holland_lines svg > .linea mask path", { drawSVG: "100% 100%" }, { duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d });
      gsap.from("#holland_lines svg > .punto > *", { duration: .3,  opacity: 0, stagger: .2, delay: this.d+1 });
    }
}
</script>

<style scoped>
</style>