<template>
  <div class="map-wrapper" id="slovenia_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

    <g class="linea" id="linea_1">
      <path mask="url(#linea1_mmask)" class="small_line_full" d="m938.62,510.86h8.63l3.14-3.14" />
      <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
        <path id="linea1_mask" class="small_line_full" d="m938.62,510.86h8.63l3.14-3.14" />
      </mask>
    </g>
    <g class="punto" id="punto_1">
      <path class="small_spot" d="m950.33,507.22c.27,0,.5.22.5.5s-.22.5-.5.5-.5-.22-.5-.5c0-.27.22-.5.5-.5h0Z" />
    </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Slovenia',
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
      gsap.to('#slovenia_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#slovenia_lines svg > .linea mask path", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d });
      gsap.from("#slovenia_lines svg > .punto > *", { duration: .3,  opacity: 0, stagger: .2, delay: this.d+1 });
    }
}
</script>

<style scoped>
</style>