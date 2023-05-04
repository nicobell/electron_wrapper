<template>
  <div :class="['map-wrapper']" id="fvg_blue">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080"
      :class="[ this.zoomlevel ]">

      <path class="fvg-shape"
        d="m942.43,515.2h-.64s.04-.43.04-.43l.39-.27-1.16-1.12-.31.03h0s-.05.05-.31.25l-.38.29h-.06s-1.89-.58-1.89-.58l-.16.16.25.36-.14.05-.66.1-.04-.07-.47-1.12-1.06-.11-.82.37-.06-.03-1.56-1.26-.21-1.25.06-.05.53-.29v-.47l-.46-.3-.87-.65.04-.09.5-.7,1.69-1.31.65-.59-.22-.77h.15s2.81.6,2.81.6l2.71.09,1.06.28-.02.11-.19.5-2.12,1.37.08.81.17.03.07-.1.27-.02.77.32.49.11.02.08v.1c0,.09,0,.13-.02.17,0,.02-.08.14-.1.18l-.99.87v.07c-.04.09-.04.12-.04.12,0,.02.06.15.13.28,0,0,.02,0,.04,0,.04,0,.09.01.12.01,0,0,.07-.03.29-.1l.35-.1.06.09.06.24-.26,1.01.22.26.49.08,1.24,1.12.31.78-.04.06-.26.27-.48.16h-.03Z" />
    </svg>
  </div>
</template>

<script>
export default {
  name: 'Fvg',
  props: {
    zoomlevel: String,
    state: Object
  },
};
</script>

<style scoped>
.fvg-shape { 
  fill: #1e85d9; 
  stroke: #fff;
  stroke-width: 0.01vw;
  transform: translateY(0.004vw);
}

.zoom-country .fvg-shape {
  transition: stroke-width 2000ms ease;
  transition-delay: 500ms;
  stroke-width: 0.01vw;
}

.zoom-europe .fvg-shape {
  transition: stroke-width 2000ms ease;
  transition-delay: 500ms;
  stroke-width: 0.01vw;
}

.zoom-fvg .fvg-shape {
  transition: stroke-width 2000ms ease;
  transition-delay: 500ms;
  stroke-width: 0.003vw;
  fill: #BCCED6;
}

.video-layer .fvg-shape {
  transition: stroke-width 2000ms ease, fill-opacity 2000ms ease;
  transition-delay: 500ms;
  stroke-width: 0.003vw;
  stroke-opacity: .8;
  fill: #FFF;
  fill-opacity: .2;
}

.map-wrapper svg { 
  transition: background-color 1000ms ease;
}

#fvg_blue {
  background-color: transparent;
  transition: background-color 1000ms ease;
}

#fvg_blue.blackground {
  background-color: rgba(0,0,0);
  transition: background-color 1000ms ease;
}

</style>