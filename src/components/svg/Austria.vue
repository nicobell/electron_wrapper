<template>
  <div class="map-wrapper" id="austria_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

      <g class="linea" id="linea_1">
        <path mask="url(#linea1_mmask)" class="small_line_full" d="m935.81,506.92l-5.45-5.45h-9.56l-1.97-1.97" />
        <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
          <path id="linea1_mask" class="small_line_full" d="m935.81,506.92l-5.45-5.45h-9.56l-1.97-1.97" />
        </mask>
      </g>
      <g class="punto" id="punto_1">
        <path class="small_spot" d="m918.7,498.96c.34,0,.62.28.62.62s-.28.62-.62.62-.62-.28-.62-.62c0-.34.28-.62.62-.62h0Z" />
      </g>

      <g class="linea" id="linea_2">
        <path mask="url(#linea2_mmask)" class="thin_line" d="m935.48,506.42l3.67-3.67v-6.04" />
        <mask id="linea2_mmask" maskUnits="userSpaceOnUse">
          <path id="linea2_mask" class="thin_line" d="m935.48,506.42l3.67-3.67v-6.04" />
        </mask>
      </g>
      <g class="punto" id="punto_2">
        <path class="thin_spot" d="m939.15,496.38c.18,0,.33.15.33.33s-.15.33-.33.33-.33-.15-.33-.33c0-.18.15-.33.33-.33h0Z" />
      </g>

      <g class="linea" id="linea_3">
        <path mask="url(#linea3_mmask)" class="small_line" d="m935.56,507.27l6.36-6.36v-5.01" />
        <mask id="linea3_mmask" maskUnits="userSpaceOnUse">
          <path id="linea3_mask" class="small_line" d="m935.56,507.27l6.36-6.36v-5.01" />
        </mask>
      </g>
      <g class="punto" id="punto_3">
        <path class="small_spot" d="m941.91,494.86c.34,0,.62.28.62.62s-.28.62-.62.62-.62-.28-.62-.62c0-.34.28-.62.62-.62h0Z" />
      </g>

      <g class="linea" id="linea_4">
        <path mask="url(#linea4_mmask)" class="medium_line" d="m937.3,506.61l6.49-6.49v-5.79" />
        <mask id="linea4_mmask" maskUnits="userSpaceOnUse">
          <path id="linea4_mask" class="medium_line" d="m937.3,506.61l6.49-6.49v-5.79" />
        </mask>
      </g>
      <g class="punto" id="punto_4">
        <path class="medium_spot" d="m943.79,493.35c.42,0,.76.34.76.76s-.34.76-.76.76-.76-.34-.76-.76c0-.42.34-.76.76-.76h0Z" />
      </g>

      <g class="linea" id="linea_5">
        <path mask="url(#linea5_mmask)" class="small_line_full" d="m937.6,507.54l7.4-7.4v-7.07" />
        <mask id="linea5_mmask" maskUnits="userSpaceOnUse">
          <path id="linea5_mask" class="small_line_full" d="m937.6,507.54l7.4-7.4v-7.07" />
        </mask>
      </g>
      <g class="punto" id="punto_5">
        <path class="small_spot" d="m944.98,491.91c.34,0,.62.28.62.62s-.28.62-.62.62-.62-.28-.62-.62c0-.34.28-.62.62-.62h0Z" />
      </g>

      <g class="linea" id="linea_6">
        <path mask="url(#linea6_mmask)" class="small_line" d="m938.53,509.66l3.71-3.71" />
        <mask id="linea6_mmask" maskUnits="userSpaceOnUse">
          <path id="linea6_mask" class="small_line" d="m938.53,509.66l3.71-3.71" />
        </mask>
      </g>
      <g class="punto" id="punto_6">
        <path class="small_spot" d="m942.41,505.07c.34,0,.62.28.62.62s-.28.62-.62.62-.62-.28-.62-.62c0-.34.28-.62.62-.62h0Z" />
      </g>

      <g class="linea" id="linea_7">
        <path mask="url(#linea7_mmask)" class="small_line_full" d="m939.46,510.64l10.87-10.87" />
        <mask id="linea7_mmask" maskUnits="userSpaceOnUse">
          <path id="linea7_mask" class="small_line_full" d="m939.46,510.64l10.87-10.87" />
        </mask>
      </g>
      <g class="punto" id="punto_7">
        <path class="small_spot" d="m950.34,499.15c.34,0,.62.28.62.62s-.28.62-.62.62-.62-.28-.62-.62c0-.34.28-.62.62-.62h0Z" />
      </g>

      <g class="linea" id="linea_8">
        <path mask="url(#linea8_mmask)" class="small_line_full" d="m939.97,511.89l16.8-16.8v-1.6" />
        <mask id="linea8_mmask" maskUnits="userSpaceOnUse">
          <path id="linea8_mask" class="small_line_full" d="m939.97,511.89l16.8-16.8v-1.6" />
        </mask>
      </g>
      <g class="punto" id="punto_8">
        <path class="small_spot" d="m956.77,492.87c.34,0,.62.28.62.62s-.28.62-.62.62-.62-.28-.62-.62c0-.34.28-.62.62-.62h0Z" />
      </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'Austria',
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
      gsap.to('#austria_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, delay: this.d })

      gsap.fromTo("#austria_lines svg > .linea mask path", { drawSVG: "0% 0%" }, {duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d+.5 });
      gsap.from("#austria_lines svg > .punto > *", { duration: .3, stagger: .2, opacity: 0, delay: this.d+1.5 });
    }
}
</script>

<style scoped>
</style>