<template>
  <div class="map-wrapper" id="dmm_lines">
    <svg version="1.1" 
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1920 1080" 
        :class="this.zoomlevel">
      

    <g class="linea_principale" id="linea_principale">
      <g mask="url(#linea_principale_mastermask)" >
        <path id="Tracciato_34054" class="cls-3" d="m940.9,513.42l-4.19,4.49,20.12,19.82,13.66,13.45v38.73s0,.44,0,.44" />
        <path id="Tracciato_34060" class="cls-1" d="m940.9,513.42l-4.19,4.49,20.12,19.82,13.66,13.45.03,38.74" />
      </g>
        
      <mask id="linea_principale_mastermask" maskUnits="userSpaceOnUse">
        <g id="linea_principale_mask">
          <path id="Tracciato_34054" class="cls-3" d="m940.9,513.42l-4.19,4.49,20.12,19.82,13.66,13.45v38.73s0,.44,0,.44" />
          <path id="Tracciato_34060" class="cls-1" d="m940.9,513.42l-4.19,4.49,20.12,19.82,13.66,13.45.03,38.74" />
        </g>
      </mask>
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea_secondaria" id="linea_secondaria">
      <g mask="url(#linea_secondaria_mastermask)" >
        <path id="Tracciato_34064" class="cls-3" d="m971.13,590.28l13.28,13.28h59.33" />
        <path id="Tracciato_34078" class="cls-1" d="m971.13,590.28l13.28,13.28h59.33l13.15,13.04" />
      </g>
        
      <mask id="linea_secondaria_mastermask" maskUnits="userSpaceOnUse">
        <g id="linea_secondaria_mask">
          <path id="Tracciato_34064" class="cls-3" d="m971.13,590.28l13.28,13.28h59.33" />
          <path id="Tracciato_34078" class="cls-1" d="m971.13,590.28l13.28,13.28h59.33l13.15,13.04" />
        </g>
      </mask>
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_1">
      <path mask="url(#L_1_mmask)" class="cls-1" d="m934.56,515.2l2.46,2.46" />
      <mask id="L_1_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_1_mask" class="cls-1" d="m934.56,515.2l2.46,2.46" />
      </mask>
    </g>
    <g class="punto overfeeder" id="P_1">
      <circle class="cls-4" cx="934.56" cy="515.2" r="1" />
      <circle class="cls-5" cx="934.56" cy="515.2" r=".4" />
    </g>


    <!-- <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_2">
      <path mask="url(#L_2_mmask)" class="cls-1" d="m946.73,517.83l-5.01,5.01" />
      <mask id="L_2_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_2_mask" class="cls-1" d="m946.73,517.83l-5.01,5.01" />
      </mask>
    </g>
    <g class="punto" id="P_2">
      <circle class="cls-4" cx="946.73" cy="517.66" r="1" />
      <circle class="cls-5" cx="946.73" cy="517.66" r=".4" />
    </g> -->


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_3">
      <path mask="url(#L_3_mmask)" class="cls-1" d="m934.3,523.05l3.72-3.72" />
      <mask id="L_3_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_3_mask" class="cls-1" d="m934.3,523.05l3.72-3.72" />
      </mask>
    </g>
    <g class="punto overfeeder" id="P_3">
      <circle class="cls-4" cx="934.3" cy="523.05" r="1" />
      <circle class="cls-5" cx="934.3" cy="523.05" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_4">
      <path mask="url(#L_4_mmask)" class="cls-1" d="m941.8,529.44l3.35-3.35" />
      <mask id="L_4_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_4_mask" class="cls-1" d="m941.8,529.44l3.35-3.35" />
      </mask>
    </g>
    <g class="punto overfeeder" id="P_4">
      <circle class="cls-4" cx="941.72" cy="529.44" r="1" />
      <circle class="cls-5" cx="941.72" cy="529.44" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_5">
      <path mask="url(#L_5_mmask)" class="cls-1" d="m953.77,569.73l16.72,16.63" />
      <mask id="L_5_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_5_mask" class="cls-1" d="m953.77,569.73l16.72,16.63" />
      </mask>
    </g>
    <g class="punto" id="P_5">
      <circle class="cls-4" cx="953.95" cy="569.86" r="1" />
      <circle class="cls-5" cx="953.95" cy="569.86" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_6">
      <path mask="url(#L_6_mmask)" class="cls-1" d="m948.94,586.36c.27.18,12.47,12.66,12.47,12.66h18.62" />
      <mask id="L_6_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_6_mask" class="cls-1" d="m948.94,586.36c.27.18,12.47,12.66,12.47,12.66h18.62" />
      </mask>
    </g>
    <g class="punto" id="P_6">
      <circle class="cls-4" cx="948.94" cy="586.36" r="1" />
      <circle class="cls-5" cx="948.94" cy="586.36" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_7">
      <path mask="url(#L_7_mmask)" class="cls-1" d="m998.64,572.99l-22.32,22.31" />
      <mask id="L_7_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_7_mask" class="cls-1" d="m998.64,572.99l-22.32,22.31" />
      </mask>
    </g>
    <g class="punto" id="P_7">
      <circle class="cls-4" cx="998.72" cy="572.94" r="1" />
      <circle class="cls-5" cx="998.72" cy="572.94" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_8">
      <path mask="url(#L_8_mmask)" class="cls-1" d="m978.42,597.6l46.37-46.21h6.02" />
      <mask id="L_8_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_8_mask" class="cls-1" d="m978.42,597.6l46.37-46.21h6.02" />
      </mask>
    </g>
    <g class="punto" id="P_8">
      <circle class="cls-4" cx="1030.7" cy="551.17" r="1" />
      <circle class="cls-5" cx="1030.7" cy="551.17" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_9">
      <path mask="url(#L_9_mmask)" class="cls-1" d="m1032.27,552.28h-8.3" />
      <mask id="L_9_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_9_mask" class="cls-1" d="m1032.27,552.28h-8.3" />
      </mask>
    </g>
    <g class="punto" id="P_9">
      <circle class="cls-4" cx="1032.47" cy="552.28" r="1" />
      <circle class="cls-5" cx="1032.47" cy="552.28" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_10">
      <path mask="url(#L_10_mmask)" class="cls-1" d="m1019.95,549.36l3.44,3.44" />
      <mask id="L_10_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_10_mask" class="cls-1" d="m1019.95,549.36l3.44,3.44" />
      </mask>
    </g>
    <g class="punto" id="P_10">
      <circle class="cls-4" cx="1019.95" cy="549.36" r="1" />
      <circle class="cls-5" cx="1019.95" cy="549.36" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_11">
      <path mask="url(#L_11_mmask)" class="cls-1" d="m980.7,599.88l30.55-30.55,3.86-3.86" />
      <mask id="L_11_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_11_mask" class="cls-1" d="m980.7,599.88l30.55-30.55,3.86-3.86" />
      </mask>
    </g>
    <g class="punto" id="P_11">
      <circle class="cls-4" cx="1015.11" cy="565.48" r="1" />
      <circle class="cls-5" cx="1015.11" cy="565.48" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_12">
      <path mask="url(#L_12_mmask)" class="cls-1" d="m1014.87,568.81h-2.9" />
      <mask id="L_12_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_12_mask" class="cls-1" d="m1014.87,568.81h-2.9" />
      </mask>
    </g>
    <g class="punto" id="P_12">
      <circle class="cls-4" cx="1015.25" cy="568.81" r="1" />
      <circle class="cls-5" cx="1015.25" cy="568.81" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_14">
      <path mask="url(#L_14_mmask)" class="cls-1" d="m1052.46,595.06l-8.61,8.61" />
      <mask id="L_14_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_14_mask" class="cls-1" d="m1052.46,595.06l-8.61,8.61" />
      </mask>
    </g>
    <g class="punto" id="P_14">
      <circle class="cls-4" cx="1052.46" cy="594.98" r="1" />
      <circle class="cls-5" cx="1052.46" cy="594.98" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_15">
      <path mask="url(#L_15_mmask)" class="cls-1" d="m1068.56,583.98l-22.16,22.16" />
      <mask id="L_15_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_15_mask" class="cls-1" d="m1068.56,583.98l-22.16,22.16" />
      </mask>
    </g>
    <g class="punto" id="P_15">
      <circle class="cls-4" cx="1068.66" cy="583.84" r="1" />
      <circle class="cls-5" cx="1068.66" cy="583.84" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_16">
      <path mask="url(#L_16_mmask)" class="cls-1" d="m1065.7,599.36l-13.13,13.13" />
      <mask id="L_16_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_16_mask" class="cls-1" d="m1065.7,599.36l-13.13,13.13" />
      </mask>
    </g>
    <g class="punto" id="P_16">
      <circle class="cls-4" cx="1065.89" cy="599.25" r="1" />
      <circle class="cls-5" cx="1065.89" cy="599.25" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_17">
      <path mask="url(#L_17_mmask)" class="cls-1" d="m1063.07,605.77l-8.54,8.54" />
      <mask id="L_17_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_17_mask" class="cls-1" d="m1063.07,605.77l-8.54,8.54" />
      </mask>
    </g>
    <g class="punto" id="P_17">
      <circle class="cls-4" cx="1063.34" cy="605.58" r="1" />
      <circle class="cls-5" cx="1063.34" cy="605.58" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_18">
      <path mask="url(#L_18_mmask)" class="cls-1" d="m1061.34,612.64l-4.17,4.17" />
      <mask id="L_18_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_18_mask" class="cls-1" d="m1061.34,612.64l-4.17,4.17" />
      </mask>
    </g>
    <g class="punto" id="P_18">
      <circle class="cls-4" cx="1061.46" cy="612.39" r="1" />
      <circle class="cls-5" cx="1061.46" cy="612.39" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_19">
      <path mask="url(#L_19_mmask)" class="cls-1" d="m1036.93,618.26l-14.4-14.4" />
      <mask id="L_19_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_19_mask" class="cls-1" d="m1036.93,618.26l-14.4-14.4" />
      </mask>
    </g>
    <g class="punto" id="P_19">
      <circle class="cls-4" cx="1037.15" cy="618.41" r="1" />
      <circle class="cls-5" cx="1037.15" cy="618.41" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_20">
      <path mask="url(#L_20_mmask)" class="cls-1" d="m1045.36,616.93l-12.95-12.95" />
      <mask id="L_20_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_20_mask" class="cls-1" d="m1045.36,616.93l-12.95-12.95" />
      </mask>
    </g>
    <g class="punto" id="P_20">
      <circle class="cls-4" cx="1045.46" cy="617.08" r="1" />
      <circle class="cls-5" cx="1045.46" cy="617.08" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_21">
      <path mask="url(#L_21_mmask)" class="cls-1" d="m1048.47,617.82l-13.95-13.95" />
      <mask id="L_21_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_21_mask" class="cls-1" d="m1048.47,617.82l-13.95-13.95" />
      </mask>
    </g>
    <g class="punto" id="P_21">
      <circle class="cls-4" cx="1048.58" cy="617.96" r="1" />
      <circle class="cls-5" cx="1048.58" cy="617.96" r=".4" />
    </g>


    <g v-show="this.stateId=='dmm_connections'" class="linea" id="L_22">
      <path mask="url(#L_22_mmask)" class="cls-1" d="m1027.35,554.74h-5.83" />
      <mask id="L_22_mmask" maskUnits="userSpaceOnUse"> 
        <path id="L_22_mask" class="cls-1" d="m1027.35,554.74h-5.83" />
      </mask>
    </g>
    <g class="punto" id="P_22">
      <circle class="cls-4" cx="1027.57" cy="554.74" r="1" />
      <circle class="cls-5" cx="1027.57" cy="554.74" r=".4" />
    </g>

    </svg>
  </div>
</template>

<script>
import gsap from 'gsap'
import { DrawSVGPlugin } from "../../libs/DrawSVGPlugin"

export default {
  name: 'DMMLines',
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
    gsap.to('#dmm_lines svg', { scale: this.state.zoom, x: this.state.x, y: this.state.y, duration: 0 })

    gsap.fromTo("#dmm_lines #linea_principale_mask path", { drawSVG: "0% 0%" }, { duration: 2, drawSVG: "0% 100%", delay: this.d+1 });
    gsap.fromTo("#dmm_lines .punto", { opacity: 0 }, { duration: 0.3,  opacity: 1, delay: this.d+2.5 });
  },
  computed: {
    stateId() { 
      return this.state.id 
    }
  },
  watch: {
    stateId() {
      if(this.stateId == "dmm_connections") {
        gsap.fromTo("#dmm_lines #linea_secondaria_mask path", { drawSVG: "0% 0%" }, { duration: 2, drawSVG: "0% 100%", delay: this.d+1 });
        gsap.fromTo("#dmm_lines .linea mask path", { opacity: 0 }, { duration: 1, opacity: 1, delay: this.d+1.5 });
      }
    }
  }
}
</script>

<style scoped>
.punto { opacity: 0; }

.cls-1,
.cls-3 {
  stroke-width: .02vw;
  fill: none;
  stroke: #999;
  stroke-dasharray: 0 0 1.78 .44;
}

.cls-3 {
  opacity: .5;
  stroke-width: .08vw;
}

.cls-4 { opacity: .3; }

.cls-4,
.cls-5 {
  fill: #a2a2a2;
}
</style>