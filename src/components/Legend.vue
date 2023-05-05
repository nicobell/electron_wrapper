<template>
    <div class="legend-bar">
        <div class="legend-label">LEGEND</div>
        <div v-for="(t, ind) in this.legendtiles" :key="'tile'+ ind" class="tile">
            <span class="text" v-html="t.label"></span>
            <span :class="['symbol', t.symbol]" :style="'background-color:' + t.color"></span>
        </div>
    </div>
</template>

<script>
export default {
    name: "Legend",
    props: {
        tiles: Array,
        legenddata: Object
    },
    data() {
        return {}
    },
    computed: {
        legendtiles() {
            var ll = []
            this.tiles.forEach(el => ll.push(this.legenddata[el]) )
            return ll
        }
    },
    methods: {},
    mounted() {}
}
</script>

<style scoped>

.legend-bar {
    position: absolute;
    z-index: 10;
    top: 0;
    right: 0;
    display: flex;
    flex-direction: row-reverse;
}

.legend-label {
    background-color: #000;
    color: #fff;
    font-size: .8vw;
    padding: .75vw 1.2vw;
    font-weight: 700;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.legend-label:before {
    position: absolute;
    content: "";
    width: 0;
    height: 0;
    border-top: 28px solid transparent;
    border-right: 11px solid black;
    border-bottom: 28px solid transparent;
    right: 111px;
}

.legend-bar .tile {
    display: flex;
    flex-direction: row;
    align-items: center;
    background-color: rgba(0, 0, 0, .4);
    padding: .75vw 1.2vw;
    border-right: 1px solid grey;
}

.legend-bar .tile:nth-child(2){
    border-right: 0px solid grey;
    padding: .75vw 1.6vw .75vw 1.2vw;
}

.legend-bar .tile .symbol {
    display: block;
}

.legend-bar .tile .symbol.square {
    width: .8vw;
    height: .8vw;
}
.legend-bar .tile .symbol.rect {
    width: .5vw;
    height: 1.5vw;
}
.legend-bar .tile .symbol.thick-rect{
    width: .7vw;
    height: 1.5vw;
}
.legend-bar .tile .symbol.thin-rect {
    width: .2vw;
    height: 1.5vw;
}
.legend-bar .tile .symbol.circle {
    width: 1vw;
    height: 1vw;
    border-radius: 50%;
}
.legend-bar .tile .symbol.logistic-hub {
    width: .8vw;
    height: .8vw;
    border: .2vw solid rgba(255, 255, 255, .7);
    border-radius: 50%;
}

.legend-bar .tile .symbol.dotted-rect-thin,
.legend-bar .tile .symbol.dotted-rect {
    width: .5vw;
    height: .5vw;
}
.legend-bar .tile .symbol.dotted-rect-thin::after,
.legend-bar .tile .symbol.dotted-rect::after {
    content: '';
    position: absolute;
    width: .5vw;
    height: .5vw;
    top: calc(50% + .5rem);
    background-color: inherit;
}
.legend-bar .tile .symbol.dotted-rect-thin::before,
.legend-bar .tile .symbol.dotted-rect::before {
    content: '';
    position: absolute;
    width: .5vw;
    height: .4vw;
    top: calc(50% - .95rem);
    background-color: inherit;
}

.legend-bar .tile .symbol.dotted-rect-thin,
.legend-bar .tile .symbol.dotted-rect-thin::after,
.legend-bar .tile .symbol.dotted-rect-thin::before {
    width: .2vw;
}

.legend-bar .tile .text {
    display: block;
    font-size: .7vw;
    line-height: .75vw;
    color: #FFF;
    margin-right: .75vw;
    text-align: right;
}
</style>