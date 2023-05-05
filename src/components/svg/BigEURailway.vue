<template>
  <div class="map-wrapper" id="big_eu_white_line">
    <svg version="1.1" 
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1920 1080" 
      :class="[this.zoomlevel, this.state.id]">

      <g id="linee">
        <path id="L1" class="line light" d="m938.85,512.07l-7.99,8.03,10.76,10.76" />
        <path id="L2" class="line light" d="m938.73,511.09l-10.39,10.39,16.83,16.83" />
        <path id="L3" class="line light" d="m936.36,512.24l-2.84,2.84h-1.41" />
        <path id="L4" class="line light" d="m936.52,512.07h-10.36l-2.5,2.5v16.87" />
        <path id="L5" class="line light" d="m935.83,511.34h-11.5l-3.73,3.73v11.7" />
        <path id="L6" class="line light" d="m936.84,510.57h-14.41l-7.72,8.2v7.06" />
        <path id="L7" class="line light" d="m935.76,509.89h-14.72l-4.44,4.44" />
        <path id="L8" class="line light" d="m935.78,509.14h-4l-9.88-9.88h-3.44" />
        <path id="L9" class="line yellow" d="m933.47,508.84l-28.1-28.1h-6.02" />
        <path id="L10" class="line yellow" d="m933.76,507.92l-39.06-39.06v-3.68l-6.06-6.06" />
        <path id="L11" class="line yellow" d="m935.23,507.29l-21.77-21.77" />
        <path id="L12" class="line light" d="m934.12,507.94v-4.02l-30.3-30.3v-8.46" />
        <path id="L13" class="line light" d="m934.9,507.56v-3.85l-9.11-9.22v-1.52l-4.1-3.99" />
        <path id="L14" class="line dark" d="m935.85,508.13v-4.96l-8.49-8.79-.1-4.71-17.47-16.79-4.01-4.01" />
        <path id="L15" class="line yellow" d="m936.84,505.67v-6.02l-3.98-4.04-2.59-2.62" />
        <path id="L16" class="line light" d="m937.63,506.7v-14.74" />
        <path id="L17" class="line white" d="m938.18,506.2v-2.03l1.67-1.73v-6.19" />
        <path id="L18" class="line light" d="m938.57,507.49v-2.91l4.17-4.31v-4.85" />
        <path id="L19" class="line yellow" d="m939.17,506.96v-1.83l5.53-5.55v-5.82" />
        <path id="L20" class="line light" d="m938.23,507.59l-.18-.12,7.93-7.93v-7.1" />
        <path id="L21" class="line light" d="m940.64,505.73l30.18-30.18v-2.15" />
        <path id="L22" class="line light" d="m940.78,506.72l27.14-26.85" />
        <path id="L23" class="line light" d="m943.09,505.93l-3.88,3.88" />
        <path id="L24" class="line light" d="m939.02,508.7h3.29l9.24-9.24" />
        <path id="L25" class="line light" d="m939.47,509.4h3.98l14.84-14.84v-1.67" />
        <path id="L26" class="line light" d="m940.41,510.04h5.58l16.62-16.6" />
        <path id="L27" class="line light" d="m939.22,510.78h8.21l3.21-3.21" />
        <path id="L28" class="line light" d="m941.12,511.61h6.75l17.71-17.86" />
        <path id="L29" class="line light" d="m941.79,512.59h6.37l22.79-22.46h17.44" />
        <path id="L30" class="line yellow" d="m942.28,513.36h16.08l15.2-15.2" />

        <path id="P1" class="point light" d="m941.62,530.14c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P2" class="point light" d="m945.16,537.66c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P3" class="point light" d="m932.11,514.43c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />  
        <path id="P4" class="point light" d="m923.65,530.79c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P5" class="point light" d="m920.59,526.13c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P6" class="point light" d="m914.71,525.2c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P7" class="point light" d="m916.47,513.86c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P8" class="point light" d="m918.57,498.62c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P9" class="point yellow" d="m899.12,479.98c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P10" class="point yellow" d="m888.6,458.41c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P11" class="point yellow" d="m913.46,484.82c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P12" class="point light" d="m903.82,464.4c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P13" class="point light" d="m921.5,488.07c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P14" class="point dark" d="m905.77,468c.4,0,.74.32.74.73,0,.4-.32.74-.73.74-.4,0-.74-.32-.74-.73,0,0,0,0,0,0,0-.4.32-.73.73-.73,0,0,0,0,0,0Z" />
        <path id="P15" class="point yellow" d="m930.25,492.28c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P16" class="point light" d="m937.63,491.15c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P17" class="point white" d="m939.85,495.42c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P18" class="point light" d="m942.74,494.62c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P19" class="point yellow" d="m944.68,492.89c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P20" class="point light" d="m945.97,491.24c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P21" class="point light" d="m970.82,472.44c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P22" class="point light" d="m968.17,479.17c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P23" class="point light" d="m943.26,505.01c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P24" class="point light" d="m951.56,498.82c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P25" class="point light" d="m958.31,492.25c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P26" class="point light" d="m962.85,492.39c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P27" class="point light" d="m950.83,506.57c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P28" class="point light" d="m965.74,492.79c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P29" class="point light" d="m988.59,489.38c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
        <path id="P30" class="point yellow" d="m973.7,497.43c.36,0,.64.29.64.64s-.29.64-.64.64-.64-.29-.64-.64h0c0-.36.29-.64.64-.64Z" />
      </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap';
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
    name: 'BigEURailway',
    props: {
      zoomlevel: String,
      state: Object,
      d: Number, 
      io: String
    },
    mounted() {
      gsap.registerPlugin(DrawSVGPlugin);

      gsap.to('.map-wrapper#big_eu_white_line svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

      gsap.fromTo("#big_eu_white_line #linee .line", { drawSVG: "0% 0%" }, { duration: .5, drawSVG: "0% 100%"/* , stagger: .1 */, delay: this.d+.5 })

      gsap.from("#big_eu_white_line #linee .point", { opacity: 0/* , stagger: .1 */, duration: .5, delay: this.d+1 });
    }
}
</script>

<style scoped>

.menu_mediterranean .line {
  stroke: #fff !important;
  stroke-width: .015vw !important;
  transition: stroke ease 500ms, stroke-width ease 500ms;
}
.menu_mediterranean .point {
  fill: #fff !important;
  transition: fill ease 500ms;
}

.point { transition: fill ease 500ms; }
.line { 
  transition: stroke ease 500ms, stroke-width ease 500ms;
}

.line.white { 
  stroke: #fff; 
  stroke-width: .015vw;
}
.point.white { 
  fill: #fff; 
}

.line.light { 
  stroke: #fdffd2; 
  stroke-width: .015vw;
}
.point.light { 
  fill: #fdffd2; 
}

.line.yellow {
  stroke: #f5e347;
  stroke-width: .025vw;
}
.point.yellow {
  fill: #f5e347;
}

.line.dark {
  stroke: #e1ac00;
  stroke-width: .05vw;
}
.point.dark {
  fill: #e1ac00;
}

.line { 
  fill: none; 
  stroke-linejoin: round;
}

</style>