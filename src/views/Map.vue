
<template>
  <div v-if="this.currentState.id" ref="appwrapper" class="about">

    <!-- //////////////////// PRIMARY TABLE INFO //////////////////// -->
    <div ref="infogrid" class="info-grid show">
      <!-- <div v-if="this.getTable(this.currentTable).title && this.currentId != 'menu_fvg' && this.currentState.parent != 'menu_fvg'" class="title-card">
        <h3>{{ this.getTable(this.currentTable).subtitle }}</h3>
        <h2>{{ this.getTable(this.currentTable).title }}</h2>
      </div> -->

      <div :class="{
        'grid': true,
        'no-title' : !this.getTable(this.currentTable).title
        }">

        <div v-if="this.getTable(this.currentTable).title" class="title-card">
          <h3>{{ this.getTable(this.currentTable).subtitle }}</h3>
          <h2>{{ this.getTable(this.currentTable).title }}</h2>
        </div>

        <div v-for="(entry, index) in this.getTable(this.currentTable).data" :key="'table_data_' + index" 
          :class="['table-entry', entry.subdata ? 'subgrid' : '']">

          <div :class="['num', entry.icon]" v-html="entry.num"></div>
          <div class="labels">
            <span class="label" v-html="entry.label" ></span>
            <span v-if="entry.sublabel" class="small-label">{{ entry.sublabel }}</span>
          </div>

          <div v-if="entry.subdata" class="subdata">
            <div v-for="(d, ind) in entry.subdata" :key="'subdata'+index+'_'+ind">
              <span class="subnum">{{ d.num }}</span>
              <span class="sublabel">{{ d.label }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- //////////////////// SECONDARY TABLE INFO //////////////////// -->
    <div ref="infocity" class="info-city">
      <h2>{{ this.getTable(this.currentFocus).title }}</h2>
      <div class="grid">
        <div v-for="(entry, index) in this.getTable(this.currentFocus).data" :key="'table_data_' + index" 
          :class="['table-entry', entry.subdata ? 'subgrid' : '']">

          <div :class="['num', entry.icon]">{{ entry.num }}</div>
          <div class="labels">
            <span class="label">{{ entry.label }}</span>
            <span v-if="entry.sublabel" class="small-label">{{ entry.sublabel }}</span>
          </div>
        </div>
      </div>
    </div>

    <div class="idle">
      <div class="idle-text">Touch to explore</div>
      <img class="icon-hand" src="../assets/icons/icon-hand.svg" width="31px" height="36px">
      <div class="idle-hand-animation"></div>
    </div>

    <div v-if="this.currentState.parent=='menu_mediterranean'" class="gradient-mediterranean">
      <img v-if="this.currentId=='dmm_connections'" src="../assets/gradient-grey.png" alt="">
      <h2 v-if="this.currentId=='dmm_connections'">Direct Nediterranean <br> Maritime Connections</h2>

      <img v-if="this.currentId=='roro_connections'" src="../assets/gradient-light-blue.png" alt="">
      <h2 v-if="this.currentId=='roro_connections'">RoRo Connections</h2>

      <img v-if="this.currentId=='feeder_connections'" src="../assets/gradient-yellow.png" alt="">
      <h2 v-if="this.currentId=='feeder_connections'">Feeder Connections</h2>

    </div>

    <!-- //////////////////// 360 VIDEOPLAYER //////////////////// -->
    <div v-if="this.visiblevideo" id="videoplayer">
      <VideoPlayerInteractive 
        :src="this.videoSrc"
        :id="this.currentState.id"
        :interactive="this.interactivevideo"
        @close-video="this.interact()" 
        :title="this.videoTitle" 
      />
    </div>

    <!-- //////////////////// NAVIGATION BUTTONS //////////////////// -->
    <div class="button-wrapper">
      <template v-for="(step, index) in this.steps" :key="'button_step' + index">
      
        <button v-if="this.recursiveParent == step && step != this.currentId"
          @click="this.zoomToState(this.currentState.parent)"
          class="backbutton">
          <span>Back</span>
        </button>

        <button v-else 
          @click="this.zoomToState(step)"
          :class="[
            this.currentId == step ? 'active' : '',
            step == 'menu_global' ? 'global': '',
            step == 'menu_mediterranean' ? 'medit': '',
            step == 'menu_europe' ? 'eu': '',
            step == 'menu_fvg' ? 'fvg': ''
          ]"> 
          <span>{{ this.getState(step).title }}</span>
        </button>

      </template>
    </div>

    <div v-if="!this.interactivevideo" :class="{
      'logo': true,
      'porti': this.currentId == 'menu_fvg' || this.currentState.parent == 'menu_fvg'
    }"></div>

    <!-- //////////////////// LABELS ON MAP //////////////////// -->
    <div v-if="this.showLabels && this.currentState.parent!='menu_fvg'" class="labels">
      <template v-for="(label, index) in this.currentState.labels" :key="'current_state_label_' + index">
        <div v-if="this.getLabel(label)"
          :style="
            'top: ' + this.getLabel(label).y + 'vh;' +
            'left: ' + this.getLabel(label).x + 'vw;'"
          :class="[
            this.getLabel(label).stateto ? 'white-arrow' : null, 
            this.getLabel(label).style, 
            this.labelOpacity(label) ? 'transparent' : '',
            this.getLabel(label).title == this.getTable(this.currentState.focus.table).title ? 'blue' : ''
          ]"
          @click="this.getLabel(label).stateto ? this.zoomToState(this.getLabel(label).stateto) : null"
        >
          <span>{{ this.getLabel(label).title }}</span>
          <span class="arrow" :style="'background-color:' + this.getLabel(label).color + ';'"></span>
        </div>
      </template>
    </div>

    <!-- //////////////////// SPOTS PORTI IN FVG STATE //////////////////// -->
    <div class="spots-wrapper" v-if="(this.currentId == 'menu_fvg' || this.currentState.parent=='menu_fvg') && this.showLabels">
      <div v-for="(spot, index) in this.currentState.labels" :key="'friuli_porti_' + index"
        :class="['spot', 
          this.getSpot(spot).icon, this.currentState.parent=='menu_fvg' ? 'small-spot' : '', 
          this.getSpot(spot).stateto==this.currentState.id ? 'active' : '' ]"
        :style="
          'top: ' + this.getSpot(spot).y + 'vh;' +
          'left: ' + this.getSpot(spot).x + 'vw;' +
          'width:' + this.getSpot(spot).radius + 'vw;' +
          'height:' + this.getSpot(spot).radius + 'vw;' +
          'display: ' + (this.getSpot(spot).radius ? 'block' : 'none')"
        @click="this.getSpot(spot).stateto ? this.zoomToState(this.getSpot(spot).stateto) : null"
      >
        {{ this.getSpot(spot).title }}
      </div>
    </div>

    <div class="videobutton"
      v-if="this.currentState.parent=='menu_fvg' && this.showLabels">
      <button @click="this.interact()"> VIRTUAL <br> TOUR </button>
    </div>
    <!-- @click="this.showvideo(this.getSpot(label))" -->

    <div ref="svgwrapper" :class="{ 'svg-wrapper' : true, 'sfondo' : !this.visiblevideo }">

      <!-- //////////////////// MORLD MAP //////////////////// -->
      <WorldSvg
        :countries="this.currentState.highlights ? this.currentState.highlights : []"
        :focus="this.currentState.focus.country"
        :zoomlevel="this.currentState.type"
        :d="this.duration"
        @country="this.manageCountryClick"
      />

      <!-- //////////////////// GENERAL LINES //////////////////// -->
      <RedLine 
        v-if="this.currentState.lines.includes('big_red_line')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState" 
        :d="this.duration"
        :io="this.inOut" />

      <SmallEURailway 
        v-if="this.isShowable('small_eu_white_line')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />
      
      <BigEURailway 
        v-if="this.currentState.lines.includes('big_eu_white_line')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />


      <!-- //////////////////// MEDITERRANEAN CONNECTIONS //////////////////// -->
      <RoRoLines 
        v-if="this.isShowable('roro_connections_line')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState" 
        :d="this.duration"
        :io="this.inOut" />

      <DMMLines 
        v-if="this.isShowable('dmm_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <FeederLines 
        v-if="this.isShowable('feeder_connections_line')" 
        :zoomlevel="this.currentState.type" 
        :state="this.currentState" 
        :d="this.duration"
        :io="this.inOut" />


      <!-- //////////////////// EUROPE COUNTRIES //////////////////// -->
      <Germany
        v-if="this.isShowable('germany_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Austria 
        v-if="this.isShowable('austria_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Italy 
        v-if="this.isShowable('italy_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Hungary 
        v-if="this.isShowable('hungary_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Holland 
        v-if="this.isShowable('holland_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Luxemburg 
        v-if="this.isShowable('luxemburg_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <CzechRep
        v-if="this.isShowable('czech_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Slovenia
        v-if="this.isShowable('slovenia_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Slovakia
        v-if="this.isShowable('slovakia_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Poland
        v-if="this.isShowable('poland_lines')"
        :zoomlevel="this.currentState.type" 
        :state="this.currentState"
        :d="this.duration"
        :io="this.inOut" />

      <Fvg
        :zoomlevel="this.currentState.type" 
        :state="this.currentState" />

      <Corridoi
        v-if="this.currentState.id=='menu_fvg'"
        :zoomlevel="this.currentState.type" 
        :d="this.duration"
        :state="this.currentState" />

      <!-- //////////////////// LEGEND COMPONENT //////////////////// -->
      <Legend v-if="this.legends && this.currentState.parent!='menu_mediterranean' && this.currentState.parent!='menu_fvg'" 
        :legenddata="this.legends" :tiles="this.dynamicLegend"/>

    </div>

  </div>
</template>

<script>
/* greensock animation library + plugin */
import gsap from 'gsap';
//import { DrawSVGPlugin } from "../libs/DrawSVGPlugin"
import { CustomEase } from "gsap/CustomEase"

import statesJSON from '../json/states.json'
import labelsJSON  from '../json/labels.json'
import spotsJSON from '../json/spots.json'
import legendsJSON from '../json/legends.json'
import tablesJSON from '../json/tables.json'

/* interactive and graphic components */
import Legend from '../components/Legend.vue'
import VideoPlayerInteractive from '../components/VideoPlayerInteractive.vue'

/* map components  */
import WorldSvg from '../components/svg/WorldSvg.vue'
import Fvg from '../components/svg/Fvg.vue'
import Corridoi from '../components/svg/Corridoi.vue'

/* railways components */
import RedLine from '../components/svg/RedLine.vue'
import SmallEURailway from '../components/svg/SmallEURailway.vue'
import BigEURailway from '../components/svg/BigEURailway.vue'

/* moving lines components */
import RoRoLines from '../components/svg/RoRoLines.vue'
import DMMLines from '../components/svg/DMMLines.vue'
import FeederLines from '../components/svg/FeederLines.vue'

/* country linews components */
import Germany from '../components/svg/Germany.vue'
import Austria from '../components/svg/Austria.vue'
import Italy from '../components/svg/Italy.vue'
import Hungary from '../components/svg/Hungary.vue'
import Holland from '../components/svg/Holland.vue'
import Luxemburg from '../components/svg/Luxemburg.vue'
import CzechRep from '../components/svg/CzechRep.vue'
import Slovenia from '../components/svg/Slovenia.vue'
import Poland from '../components/svg/Poland.vue'
import Slovakia from '../components/svg/Slovakia.vue'

export default {
  name: 'Map',
  components: { 
    //components
    VideoPlayerInteractive,
    Legend,

    //mappa
    WorldSvg, 
    Fvg,
    Corridoi,

    //main lines
    RedLine,
    SmallEURailway,
    BigEURailway,
    
    //mediterranean lines
    FeederLines,
    RoRoLines,
    DMMLines,

    //country lines
    Germany,
    Austria,
    Hungary,
    Holland,
    Luxemburg,
    Poland,
    Slovakia,
    Italy,
    Slovenia,
    CzechRep
  },
  data() {
    return {
      currentId: 'menu_global',
      currentTable: 'global',
      currentFocus: '',
      prevId: null,

      showLabels: false,
      enableButtons: false,
      labels: {},
      spots: {},
      states: [],
      tables: [],
      legends: null,
      steps: ['menu_global', 'menu_mediterranean', 'menu_europe', 'menu_fvg'],
      visiblevideo: false,
      interactivevideo: false,
      inOut: 'in',
      customduration: 0,
      timeoutLabels: null,
      timeoutIdle: null,
      
      videoSrc: [],
      videoTitle: ""
    }
  },
  computed: {
    prevType() {
      if(this.prevId)
        return this.getState(this.prevId).type
      else
        return "zoom-global"
    },
    duration() {
      //animation duration based on state zoom level transition
      let d = 1

      if(  (this.prevType=='zoom-fvg' && this.currentState.type=='zoom-global') || (this.prevType=='zoom-global' && this.currentState.type=='zoom-fvg')
        || (this.prevType=='zoom-fvg' && this.currentState.type=='zoom-europe') || (this.prevType=='zoom-europe' && this.currentState.type=='zoom-fvg')
        || (this.prevType=='zoom-europe' && this.currentState.type=='zoom-global') || (this.prevType=='zoom-global' && this.currentState.type=='zoom-europe')
        || (this.prevType=='zoom-country' && this.currentState.type=='zoom-global') || (this.prevType=='zoom-global' && this.currentState.type=='zoom-country') )
        d = 3

      else if(  (this.prevType=='zoom-fvg' && this.currentState.type=='zoom-country') || (this.prevType=='zoom-country' && this.currentState.type=='zoom-fvg') )
        d = 2

      else if((this.prevType=='zoom-europe' && this.currentState.type=='zoom-country') || (this.prevType=='zoom-country' && this.currentState.type=='zoom-europe'))
        d = 1.5

      else if( this.prevType==this.currentState.type && this.prevType=='zoom-country' )
        d = 1.5

      else if( this.prevType==this.currentState.type && this.currentState.type!='video-layer')
        d = 2

      return d
    },
    currentState() {
      let s = { lines: [], parent: "" }
      if(this.getState(this.currentId).lines)
        s = this.getState(this.currentId)
      return s
    },
    //get tree branch parent of state to level 0 (Global, Mediterranean, Central EU, FVG)
    recursiveParent() {
      if(this.currentState.parent != "") {
        let sp = this.getState(this.currentState.parent)
        while(sp.parent != "")
          sp = this.getState(sp.parent)

        return sp.id

      } else 
        return this.currentId
    },
    //legend based on tree branch of state
    dynamicLegend() {
      let tiles = []
      if(this.currentId == "menu_global")
        tiles = ['ditc', 'dimc']

      if(this.currentId == "menu_mediterranean" || this.recursiveParent == "menu_mediterranean")
        tiles = ['ditc', 'roro', 'feeder', 'dimc', 'dmmc']
      
      if(this.currentId == "menu_europe")
        tiles = ['train16plus', 'train816', 'train08']
      
      if(this.recursiveParent == "menu_europe" && this.currentId != "menu_europe")
        tiles = ['rwv', 'rwnv', 'train16plus', 'train816', 'train08', 'ditc2', 'oc']

      if(this.currentId == "menu_fvg")
        tiles = ['rc', 'hc', 'lh', 'bac', 'mc']

      return tiles.reverse()
    }
  },
  methods: {
    manageCountryClick(id) {
      this.zoomToState(id)
    },
    zoomToState(id) {
      //parameter to control enabling of buttons for animations, all disabled while another one is running, to avoid conflicts popping up
      //also, do not execute again zoomToState() if we already are in the same state
      if(id != this.currentId && this.enableButtons) {

        //get next state to compute animation and state
        let nextstate = this.getState(id)

        //disable buttons during animation
        this.enableButtons = false
        
        //disabilito le LABELS solo se mi sposto tra stati che non mantengono la stessa "vista", cioè
        //--> SE vado in una città all'interno di uno stato, 
        //--> SE torno da una città al suo country padre
        //--> SE vado da un porto all'altro nella sezione FVG
        if(nextstate.focus.city 
          || (nextstate.focus.country && (id == this.currentState.parent)) 
          || (nextstate.parent == this.currentState.parent && nextstate.parent == 'menu_fvg') 
        )
          this.showLabels = true
        else
          //ALTRIMENTI nel caso normale le nascondo
          this.showLabels = false

        //se torno allo stato padre, il parametro definisce la direzione 'out'
        if(id === this.currentState.parent)
          this.inOut = 'out'
        else
          this.inOut = 'in'

        //animazione tabella info
        if(this.currentTable!=nextstate.table)
          this.$refs.infogrid.classList.remove('show')
      
        //animazione tabella city
        if(this.currentFocus!=nextstate.focus.table)
          this.$refs.infocity.classList.remove('show')

        //aggiorna il prossimo stato per calcolare il parametro this.duration in base alla partenza e all'arrivo
        this.prevId = this.currentId
        this.currentId = nextstate.id
        
        //serve anche un parametro customduration per calcolare al volo i casi particolari in cui mi muovo in modo istantaneo tra uno stato e l'altro,
        //(non ho bisogno di tempo per le animazioni da che cambiano solo le label)
        //non solo in base al livello di zoom come fa this.duration, cioè
        //--> SE mi muovo ...
        if(
          (id==this.getState(this.prevId).parent && nextstate.focus.country && this.getState(this.prevId).focus.city)               //...da city a country padre
          || (nextstate.parent==this.getState(this.prevId).id && nextstate.focus.city && this.getState(this.prevId).focus.country)  //...da country a city figlia
          || (nextstate.focus.city && this.getState(this.prevId).focus.city && nextstate.parent==this.getState(this.prevId).parent) //...da city a city nello stesso country padre
        )
          this.customduration =  0
        else 
          this.customduration = this.duration

        //ritardo nel cambio delle tabelle per permettere l'animazione di uscita
        setTimeout(() => { this.currentTable = nextstate.table }, 1000);
        setTimeout(() => { this.currentFocus = nextstate.focus.table }, 800);

        this.closevideo()
        if(nextstate.type=='video-layer')
          setTimeout(() => { this.showvideo() }, 1000)

        //only move fvg if next state is focus on fvg
        var totransform = ''
        if(id == "menu_fvg")
          totransform = '#fvg_blue'

        gsap.to('.map-wrapper' + totransform + ' svg', {
          duration: this.customduration,
          scale: nextstate.zoom,
          x: nextstate.x, 
          y: nextstate.y,
          ease: CustomEase.create("custom", "M0,0 C0.268,0.03 0.392,0.16 0.392,0.16 0.506,0.282 0.532,0.377 0.568,0.5 0.638,0.74 0.698,0.988 1,1 "),
          onComplete: () => {

            if(totransform == '#fvg_blue') {
              gsap.to('.map-wrapper #world_map', {
                scale: nextstate.zoom,
                x: nextstate.x, 
                y: nextstate.y,
                duration: 0
              })
            }

            //necessario ritardo dato che animazione indipendente da movimenti svg nel caso di customduration==0
            setTimeout(() => {
              if(this.currentState.table) {
                this.$refs.infogrid.classList.remove('porti')
                this.$refs.infogrid.classList.remove('fvg')

                this.$refs.infogrid.classList.add('show')

                if(this.currentState.parent=='menu_fvg')
                  this.$refs.infogrid.classList.add('porti')

                if(this.currentState.id=='menu_fvg')
                  this.$refs.infogrid.classList.add('fvg')
              }

              if(this.currentState.focus.table)
                this.$refs.infocity.classList.add('show')
            }, 800);

            //this.timeoutLabels = 
            setTimeout(() => { 
              this.enableButtons = true
              this.showLabels = true
            }, 1000);

          }
        })
      
      }
    },

    //serve un parametro esterno computed altrimenti il valore viene aggiornato ad ogni update e ridisegna le linee
    isShowable(svg) {
      return this.currentState.lines.includes(svg)
    },
    getSpot(id) {
      if(this.spots.filter(t => t.id == id).length)
        return this.spots.filter(t => t.id == id)[0]
      else
        return {}
    },
    getTable(id) {
      if(this.tables.filter(t => t.id == id).length)
        return this.tables.filter(t => t.id == id)[0]
      else return {}
    },
    getLabel(id) {
      return this.labels[id]
    },
    labelOpacity(id) {
      if(this.currentState.focus.city) {
        if(this.currentState.focus.city == id)
          return false
        else 
          return true

      } else 
        return false
    },
    getState(id) {
      if(this.states.filter(s => s.id == id).length)
        return this.states.filter(s => s.id == id)[0]
      else return {}
    },
    //VIDEO FUNCTIONS
    closevideo() { 
      this.visiblevideo = false 
      this.videoSrc = []
      this.videoTitle = ""
    },
    showvideo() {
      this.visiblevideo = true
      this.videoSrc = this.currentState.videosrc
      this.videoTitle = this.currentState.title
    },
    interact() {
      this.interactivevideo = !this.interactivevideo
    },
    resetIdle() {
      this.$refs.appwrapper.classList.remove('idle')
      clearTimeout(this.timeoutIdle)
    },
    setupIdle() {
      this.timeoutIdle = setTimeout(() => {
        this.interactivevideo = false
        this.$refs.appwrapper.classList.add('idle')
      }, 120000);
    }
  },
  mounted() {
    /* await fetch('/json/states.json')
      .then(res => res.json())
      .then(json => { this.states = json.states })

    await fetch('/json/labels.json')
      .then(res => res.json())
      .then(json => { this.labels = json.labels })

    await fetch('/json/tables.json')
      .then(res => res.json())
      .then(json => { this.tables = json.tables })

    await fetch('/json/legends.json')
      .then(res => res.json())
      .then(json => { this.legends = json.legends })
  
    await fetch('/json/spots.json')
      .then(res => res.json())
      .then(json => { this.spots = json.spots }) */

    gsap.registerPlugin(CustomEase);

    this.states = statesJSON.states
    this.labels = labelsJSON.labels
    this.tables = tablesJSON.tables
    this.legends = legendsJSON.legends
    this.spots = spotsJSON.spots
    
    setTimeout(() => {
      this.showLabels = true
      this.enableButtons = true
    }, 2000);
  },
  created() {
    this.setupIdle()

    window.addEventListener('touchstart', () => {
      //console.log('reset timer touch')
      this.resetIdle()
      this.setupIdle()
    })

    window.addEventListener('click', () => {
      //console.log('reset timer click')
      this.resetIdle()
      this.setupIdle()
    })

    window.addEventListener('contextmenu', function(e) {
      e.preventDefault();
    });
  }
}
</script>

<style>


.about::after {
    content: '';
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    pointer-events: none;
    position: absolute;
    z-index: 0;
    background-image: url(../assets/sfumatura_dark_sx.png);
    background-repeat: no-repeat;
    background-size: contain;
    background-position: left top;
}

.about .idle {
  opacity: 0;
  transition: opacity 2000ms ease;
  pointer-events: none;
  position: absolute;
  z-index: 1000;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url(../assets/idle_sfondo.png);
  background-size: contain;
  background-position: center center;
  background-repeat: no-repeat;
  cursor: pointer;
}

.about .idle .idle-hand-animation {
  position: absolute;
  width: 200px;
  height: 200px;
  border-radius: 550px;
  transform-origin: center;
  transform: scale3d(0.21,0.21,0.21);
  background: #fff;
  opacity: 0.2;
  animation: loopIdle 0.8s cubic-bezier(0.34, 0.12, 0.9, 0.59) infinite;
  top: 72%;
  left: 44.3%;
}

@keyframes loopIdle {
  from { 
    opacity: 0.2;
    transform: scale3d(0.21,0.21,0.21);
   }
  to {
    opacity: 0;
    transform: scale3d(1.3,1.3,1.3);
  }
}

.about .idle .icon-hand {
  position: absolute;
  bottom: 11%;
  left: 50%;
  transform: translateX(-50%);
  font-size: 2vw;
  color: #fff;
  font-weight: 300;
  width: 60px;
  height: 100px;
}

.about .idle .idle-text {
  position: absolute;
  bottom: 6%;
  left: 50%;
  transform: translateX(-50%);
  font-size: 2vw;
  color: #fff;
  font-weight: 300;
}

.about.idle .idle {
  pointer-events: all;
  opacity: 1;
  transition: opacity 2000ms ease;
}

/* -------------------------------------------------------- */

.static-map-wrapper,
.map-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  height: 100%;
}

.svg-wrapper {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  position: relative;
}

.svg-wrapper.sfondo {
  background: url(../assets/sfondo_principale.png);
}

.logo {
  background-image: url(../assets/logo_logisticafvg.svg);
  width: 25vw;
  height: 100%;
  max-height: 8.5vw;
  background-size: contain;
  background-repeat: no-repeat;
  position: fixed;
  z-index: 10;
  top: 1.5vw;
  left: 0.5vw;
  transition: all ease 2000ms;
}

.logo.porti {
  max-height: 11.5vw;
  height: 100%;
  transition: all ease 2000ms;
}

.gradient-mediterranean {
  position: fixed;
  top: 0;
  right: 0;
  width: 50vw;
  height: 100vh;
  z-index: 1;
  pointer-events: none;
  opacity: 0;
  animation-name: fadein;
  animation-duration: 1000ms;
  animation-fill-mode: forwards;
}

@keyframes fadein {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}

.gradient-mediterranean h2 {
  font-size: 2vw;
  color: #fff;
  font-weight: 500;
  position: absolute;
  top: 4vw;
  z-index: 1;
  right: 8vw;
}

.gradient-mediterranean img {
  position: relative;
  width: 100%;
  z-index: 0;
  opacity: .8;
  height: 100%;
}

</style>