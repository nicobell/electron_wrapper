<template>
  <div class="map-wrapper" id="slovakia_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

    <g class="linea" id="linea_1">
      <path mask="url(#linea1_mmask)" class="small_line_full" d="m941.44,513.36h5.28l23.22-22.74h18.4" />
      <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
        <path id="linea1_mask" class="small_line_full" d="m941.44,513.36h5.28l23.22-22.74h18.4" />
      </mask>
    </g>
    <g class="punto" id="punto_1">
      <path class="small_spot" d="m988.33,490.03c.26,0,.47.21.47.47s-.21.47-.47.47-.47-.21-.47-.47c0-.26.21-.47.47-.47h0Z" />
    </g>

    <g class="linea" id="linea_2">
      <path mask="url(#linea2_mmask)" class="small_line_full" d="m939.89,512.54h6.28l18.1-18.1" />
      <mask id="linea2_mmask" maskUnits="userSpaceOnUse">
        <path id="linea2_mask" class="small_line_full" d="m939.89,512.54h6.28l18.1-18.1" />
      </mask>
    </g>
    <g class="punto" id="punto_2">
      <path class="small_spot" d="m964.17,493.89c.26,0,.47.21.47.47s-.21.47-.47.47-.47-.21-.47-.47c0-.26.21-.47.47-.47h0Z" />
    </g>

    <g class="linea" id="linea_3">
      <path mask="url(#linea3_mmask)" class="small_line_full" d="m938.16,509.82h7.27l15.71-15.71" />
      <mask id="linea3_mmask" maskUnits="userSpaceOnUse">
        <path id="linea3_mask" class="small_line_full" d="m938.16,509.82h7.27l15.71-15.71" />
      </mask>
    </g>
    <g class="punto" id="punto_3">
      <path class="small_spot" d="m961.32,493.42c.26,0,.47.21.47.47s-.21.47-.47.47-.47-.21-.47-.47c0-.26.21-.47.47-.47h0Z" />
    </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Slovakia',
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
      gsap.to('#slovakia_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#slovakia_lines svg > .linea mask path", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d });
      gsap.from("#slovakia_lines svg > .punto > *", { duration: .3,  opacity: 0, stagger: .2, delay: this.d+1 });
    }
}
</script>

<style scoped>
</style>