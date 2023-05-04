<template>
  <div class="map-wrapper" id="italy_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

      <g class="linea" id="linea_1">
        <path mask="url(#linea1_mmask)" class="small_line_full" d="m937.98,512.59l-7.57,7.6,10.2,10.2" />
        <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
          <path id="linea1_mask" class="small_line_full" d="m937.98,512.59l-7.57,7.6,10.2,10.2" />
        </mask>
      </g>
      <g class="punto" id="punto_1">
        <path class="small_spot" d="m940.6,529.69c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7c0-.39.31-.7.7-.7h0Z" />
      </g>

      <g class="linea" id="linea_2">
        <path mask="url(#linea2_mmask)" class="small_line_full" d="m937.86,511.66l-9.85,9.85,15.94,15.94" />
        <mask id="linea2_mmask" maskUnits="userSpaceOnUse">
          <path id="linea2_mask" class="small_line_full" d="m937.86,511.66l-9.85,9.85,15.94,15.94" />
        </mask>
      </g>
      <g class="punto" id="punto_2">
        <path class="small_spot" d="m944.12,536.75c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7c0-.39.31-.7.7-.7h0Z" />
      </g>

      <g class="linea" id="linea_3">
        <path mask="url(#linea3_mmask)" class="small_line_full" d="m937.3,511.07l-4.37,4.37h-1.33" />
        <mask id="linea3_mmask" maskUnits="userSpaceOnUse">
          <path id="linea3_mask" class="small_line_full" d="m937.3,511.07l-4.37,4.37h-1.33" />
        </mask>
      </g>
      <g class="punto" id="punto_3">
        <path class="small_spot" d="m931.59,514.74c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7c0-.39.31-.7.7-.7h0Z" />
      </g>

      <g class="linea" id="linea_4">
        <path mask="url(#linea4_mmask)" class="small_line_full" d="m935.77,512.59h-9.82l-2.37,2.37v15.98" />
        <mask id="linea4_mmask" maskUnits="userSpaceOnUse">
          <path id="linea4_mask" class="small_line_full" d="m935.77,512.59h-9.82l-2.37,2.37v15.98" />
        </mask>
      </g>
      <g class="punto" id="punto_4">
        <path class="small_spot" d="m923.43,530.39c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7c0-.39.31-.7.7-.7h0Z" />
      </g>

      <g class="linea" id="linea_5">
        <path mask="url(#linea5_mmask)" class="small_line_full" d="m936.41,511.9h-12.2l-3.54,3.54v11.08" />
        <mask id="linea5_mmask" maskUnits="userSpaceOnUse">
          <path id="linea5_mask" class="small_line_full" d="m936.41,511.9h-12.2l-3.54,3.54v11.08" />
        </mask>
      </g>
      <g class="punto" id="punto_5">
        <path class="small_spot" d="m920.68,526.34c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7c0-.39.31-.7.7-.7h0Z" />
      </g>

      <g class="linea" id="linea_6">
        <path mask="url(#linea6_mmask)" class="small_line_full" d="m937.3,511.18h-14.88l-7.31,7.77v6.69" />
        <mask id="linea6_mmask" maskUnits="userSpaceOnUse">
          <path id="linea6_mask" class="small_line_full" d="m937.3,511.18h-14.88l-7.31,7.77v6.69" />
        </mask>
      </g>
      <g class="punto" id="punto_6">
        <path class="small_spot" d="m915.19,525.12c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7c0-.39.31-.7.7-.7h0Z" />
      </g>

      <g class="linea" id="linea_7">
        <path mask="url(#linea7_mmask)" class="small_line_full" d="m937.14,509.81h-15.59l-4.93,4.93" />
        <mask id="linea7_mmask" maskUnits="userSpaceOnUse">
          <path id="linea7_mask" class="small_line_full" d="m937.14,509.81h-15.59l-4.93,4.93" />
        </mask>
      </g>
      <g class="punto" id="punto_7">
        <path class="small_spot" d="m916.62,514.04c.39,0,.7.31.7.7s-.31.7-.7.7-.7-.31-.7-.7c0-.39.31-.7.7-.7h0Z" />
      </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Italy',
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
      gsap.to('#italy_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#italy_lines svg > .linea mask path", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d });
      gsap.from("#italy_lines svg > .punto > *", { duration: .3,  opacity: 0, stagger: .2, delay: this.d+1 });
    }
}
</script>

<style scoped>
</style>