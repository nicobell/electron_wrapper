<template>
  <div class="map-wrapper" id="poland_lines">
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" >

    <g class="linea" id="linea_1">
      <path mask="url(#linea1_mmask)" class="small_line_full" d="m937.86,506.99l32.98-32.98" />
      <mask id="linea1_mmask" maskUnits="userSpaceOnUse">
        <path id="linea1_mask" class="small_line_full" d="m937.86,506.99l32.98-32.98" />
      </mask>
    </g>
    <g class="punto" id="punto_1">
      <path class="small_spot" d="m970.84,473.17c.46,0,.83.37.83.83s-.37.83-.83.83-.83-.37-.83-.83c0-.46.37-.83.83-.83h0Z" />
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
      gsap.to('#poland_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#poland_lines svg > .linea mask path", { drawSVG: "0% 0%" }, { duration: 1, drawSVG: "0% 100%", stagger: .2, delay: this.d });
      gsap.from("#poland_lines svg > .punto > *", { duration: .3,  opacity: 0, stagger: .2, delay: this.d+1 });

      /* gsap.from("#poland_lines #other_connections path", { duration: 0.5,  opacity: 0, delay: this.d+1.5 });
      gsap.from("#poland_lines #other_connections circle", { duration: 0.5,  opacity: 0, delay: this.d+1.5 }); */
    }
}
</script>

<style scoped>
</style>