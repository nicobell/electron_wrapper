<template>
  <div 
    :class="{
      'map-wrapper': true,
      'clickable': this.zoomlevel=='zoom-country' || this.zoomlevel=='zoom-europe'
    }"
  >
    <svg
      ref="worldmap"
      id="world_map"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1920 1080"
      :class="this.zoomlevel"
    >
      <g>
        <path 
          class="cls-2" 
          d="m1014.53,424.77l.04-.22,2.94-1.67,2.19.92,3.64-3.46.09.04,3.55,1.97,3.46-.39.22,3.11,1.8-.92,2.94-1.8,1.45,2.02,2.02.7-.18,2.02-1.27,1.67,1.8,1.8-1.05,2.76,2.19,1.27,1.27,4.91,2.72.22-.35,4.38,3.64-.92v1.84l2.02,1.62-2.94,3.46-5.3-.7.22,6.01h1.45v4.21l-4.56.18-1.84,2.37-.18,4.38-2.37-2.54-2.76,1.27-1.97-.18-.75-2.19-2.19,2.72-2.94-3.29-2.37,2.76s-2.94-3.86-5.3-3.86-10.56-.88-11.7-.7c-1.05.18-6.36,4.56-6.36,4.56l-.22-5.65-2.37-1.67,1.49-2.54s2.54-2.19,2.72-2.94c.18-.7-1.45-5.48-1.62-6.22-.22-.7-.39-3.99-.39-3.99,0,0,3.51.35,5.13-.18,1.62-.57,5.83-2.02,5.83-3.11s1.1-5.87,1.1-5.87l5.3-3.46-1.1-1.27.88-3.42Z"
          ></path>
        <path
          class="cls-2"
          d="m1126.04,632.05l3.94.31,3.11,3.33,3.73.09c1.49,2.81,3.9,6,5.96,9.55,3.94,6.84,7.54,14.11,12.97,17.01l-.39.7,4.69,7.41,11.79,1.36s1.58.88,3.16,2.02c1.36,1.01,2.76,2.19,3.11,3.2.83,2.19-6.84,12.62-6.84,12.62l-13.72,4.08-1.1.22-17.23,3.38-9.03,8.5-1.67-1.67-19.99-1.67-.83,5.79-3.9,1.31c-4.08-8.59-17.18-29.02-17.18-29.02l-21.92-40.25-2.45-1.39s-1.75.13-2.54.13l-.22-8.33.75-1.45c1.32,1.67,5.7,1.8,7.1,1.8,1.67,0,2.54-2.72,8.24-5.08,5.65-2.41-.75-7.14-2.37-8.59-1.67-1.45.7-2.59,6.18-3.46,2.15-.35,4.16-.61,6.05-.61,2.89,0,5.57.48,8.55,1.71,4.95,1.97,23.23,16.26,23.23,16.26l8.81.75Z"
          ></path>
        <path
          class="cls-2"
          d="m1138.09,544.39c2.85,3.46,5.39,9.51,4.12,16.57-.61,3.64-1.31,6.14-1.4,8.06-1.75-.61-2.98-1.27-2.98-1.27l-2.19-2.5s1.14-4.91-.53-4.91c-1.4,0-5.35,4.91-8.9,5.61l-.39-6.18-3.33-1.93-.53-3.24-2.19-2.5,1.36-1.62-3.55-1.67,1.1-1.93,3.81.83,3.33,1.93.79-1.62-1.62-1.67-.18-3.24,3.2,1.05,2.45,3.02,3.55,1.1,4.08-3.9Z"
          ></path>
        <path
          class="cls-2"
          d="m1133.75,620.04l4.25,7.19c-.13.09-.26.18-.39.26-2.85-1.18-6.97-2.98-7.63-1.88-.53.96-2.76,4.51-3.94,6.44l-8.81-.75s-18.28-14.29-23.23-16.26c-2.98-1.23-5.65-1.71-8.55-1.71l-2.5-9.69s.04-.04.09-.04c9.91-6,13.98-7.67,13.98-13.94s.31-6.57,2.5-8.24c1.31-1.01,4.6-3.68,7.01-5.65.92,0,1.71.13,2.28.44,1.84,1.01,5.44,1.62,7.93,1.93l1.67,5.74,1.1,1.93,5.17,1.1-1.05,3.02-2.19,2.72-.31,5.48-2.19.83,3.55,2.45,1.67,5.22s6.57,1.36,7.67,4.95c1.1,3.55,1.93,8.46,1.93,8.46Z"
          ></path>
        <path
          class="cls-2"
          d="m1136.82,635.78l-3.73-.09-3.11-3.33-3.94-.31c1.18-1.93,3.42-5.48,3.94-6.44.66-1.1,4.78.7,7.63,1.88-1.5,1.05-2.54,2.87-2.55,2.93s.84,3.65,1.77,5.36Z"
          ></path>
        <path
          class="cls-2"
          d="m1126.21,565.94c-.69.18-1.39.15-2.05-.11-.07-.04-.15-.04-.18-.11v-2.56l-1.1-.55-.4-1.64h-1.97l-1.28-1.28-2.19-1.02-3.58-1.35-3.54-1.1.26-6.32-.07-.07,2.26-.84,5.26-.15,3.51,1.64-1.35,1.61,2.19,2.52.51,3.21,3.32,1.94.4,6.17Z"
          ></path>
        <path
          class="cls-2"
          d="m1126.62,548.04l-.8,1.61-3.32-1.94-3.8-.84-1.1,1.94.04.04-5.26.15-2.26.84-4.31-3.21h-7.89c1.64-2.74,3.14-7.74-2.59-11.4-1.79-1.1-3.51-2.41-5.19-3.69l1.97-.77,7.41,2.45,4.64-.26,6.57,4.13,1.64,1.61,3.29-1.1,3.84-.51,1.39,1.02,2.19,4.38,1.75.62.15,3.25,1.64,1.68Z"
          ></path>
        <path
          class="cls-2"
          d="m1123.98,563.15v2.59c-2.67-1.23-5.61-3.68-7.76-4.51l.83-2.54,2.19,1.01,1.27,1.27h1.97l.39,1.67,1.1.53Z"
          ></path>
        <path
          class="cls-2 turkey"
          d="m1011.66,555.67l3.7-2.3,2.5-.2,2,1.2,8.4.1-.3-1.9,5.9-.8-3-.4-1.9-1.5.5-1.7h-.1c.9.2,2.1.4,3.3.5,1.2.2,2.5.3,3.7.3,1.1,0,2.2-.1,3.3-.3.5-.1,1-.3,1.5-.5s.9-.5,1.3-.8c.9-.7,2-1.3,3-1.8s2.2-.9,3.5-1.4c2.2-.8,4-1.2,4-1.2l20.2,5s2.9.2,6.5.5c3.4.2,8.1.5,11.7.5,3.2,0,5-.2,5.3-.6.5-.5.9-1.1,1.3-1.8h7.9l4.4,3.3-.3,6.3,3.5,1.1,3.6,1.4-.8,2.5c-.4-.2-.9-.3-1.3-.3-.3,0-.6.1-.9.3-.4.3-.7,1-.8,1.9-.1,1,0,2,.1,3,.2,1.3.4,2.6.7,3.9l1.4,3.6,1.4,4.6c-2.1-.3-6-.9-7.9-1.9-.5-.3-1.3-.4-2.3-.4-2.3.1-5.5,1-8.2,1.8-1.6.5-3.2.9-4.3,1.1-.7.1-1.4.3-2.1.5s-1.4.5-2,.8c-.7.3-1.3.6-2,.8-.6.2-1.2.3-1.8.3-.4,0-.8-.1-1.1-.2-.5-.3-1.1-.4-1.7-.5-.7-.1-1.4-.2-2.2-.2-2.2,0-4.5.5-5.7,1.2l-4.4-1.9,1,5.2-2.4.3-1,.2c0-.3-.1-.5-.2-.8-.1-.2-.2-.4-.4-.5-1.9-1.6-3.4-2.3-4.7-2.3-.3,0-.7,0-1,.1-.4.1-.7.2-1,.4-.7.4-1.4.9-2.1,1.7-1.5,1.1-3.9,3.5-3.9,3.5l-7.3.9-4.6-4.4-6.7-2-1.8,4.3-5.5.7-2.7-1.4v-2.5l-.8-.8-.7,1.1-2.3-2.2-1.5,1.2-.7-.8-3.5.8-.8-.6,3.8-.9,1.9-1-6.2.1-.5-.6,2.1-1.4-.7-1.1-1.5.2-.2-2.7,1-2-3.8-2-1.8-1,1-.5-.1-2.2h.9l.6,2.6,2.8-.4-2.2-2.6,1.8-.8-1-1.6-1.1-1.7,2.1-2.3-5.1.2,1.3-4.3h0m.41-1.18h0s-.2-.5-.5-.9c-.3-.6-.6-1-.9-1.2l2.8-2.8,1.2-2.2-1.3-3.2,3.8-1.8,2.2.8h4.2c.1.1.2.3.3.5h0l.1.1c.4.6.9,1.1,1.4,1.6s1.1,1,1.7,1.4c1.1.8,2,1.4,2,1.4h0l-.6,1.6-2.4.1-2.2-1.1-3.9.5-3.7,2.9-4.2,2.3h0m-.51,9.38l-2.8-1.8,3.2-1.1,1.3,2.8-1.7.1Z"
          ></path>
        <path
          class="cls-2"
          d="m1082.95,603.65c-9.73,6.01-10.3,6.79-14.68,5.44-2.1-.66-2.24-2.32-1.67-3.94.61-1.8,2.06-3.55,2.76-3.99,1.36-.83,1.67-4.91.26-6.05-.57-.44-1.71-.39-2.76-.22,1.27-3.9,2.24-7.63,1.8-9.69l.96-.22,2.45-.26-1.05-5.22,4.38,1.93c2.19-1.36,7.36-1.67,9.55-.53,2.19,1.05,5.48-1.67,9.03-2.19,2.89-.48,8.77-2.85,12.54-2.94-2.41,1.97-5.7,4.65-7.01,5.65-2.19,1.67-2.5,1.93-2.5,8.24s-4.08,7.93-13.98,13.94c-.04,0-.04.04-.09.04Z"
          ></path>
        <path
          class="cls-2"
          d="m1015.15,492.19c-.39.75-1.14,1.67-2.24,2.28-2.02,1.1-4.65.96-4.65.96,0,0-1.49,1.23-2.72,1.36-1.23.13-2.32-1.93-2.32-1.93h-5.92l-1.36-1.1-3.16,1.8-3.55-4.38v-.04c.18-.57,1.4-4.47,1.93-4.47.31,0,1.01-.48,1.53-.92.39-.26.66-.48.66-.48l-.96-3.29,5.48-7.54,2.59-.13.26-5.87-1.62-.44.39-1.62-1.71-1.27s5.3-4.38,6.36-4.56c1.14-.18,9.34.7,11.7.7s5.3,3.86,5.3,3.86l2.37-2.76,2.94,3.29,2.19-2.72.75,2.19,1.97.18,2.76-1.27,2.37,2.54.18-4.38,1.84-2.37,4.56-.18,3.73-.09-.04-2.5,3.02.44.26,1.1,1.67-.96,2.72-1.23,1.53,2.19,2.98,3.99h-2.32l.44,4.21,5.74-.39-.13,3.29,1.1-.13.13,2.59,1.36,3.02,2.06-1.93s2.59,2.63,3.73,2.63c1.05,0,4.21-1.93,4.21-1.93,0,0,2.37,5.35,3.42,4.51,1.14-.83,2.19-1.36,2.19-1.36l3.73,3.02s2.45,1.36,3.42,1.36,3.16.13,3.02.66c-.13.57-.96,3.16-.96,3.16l-3.02.57,3.29,1.49-3.02,2.76s2.89,1.49,2.76,2.72c-.13,1.23.26,2.89-1.67,2.89s-5.48-.13-6.71,1.1c-.7.7-1.49,3.46-2.02,5.57-3.33.75-6.75,2.02-9.2,2.89-3.64,1.32-9.12,2.59-9.86,4.6-.31.79-.35,1.75-.13,2.67l-5.48-2.45-2.15,1.1c-2.37-.18-5.87.04-6.31-.79-.53-1.1,1.27-5.13-2.72-3.99-4.03,1.05-7.67,5.08-8.77,7.1-.92,1.67-1.45,2.06-2.32,4.03-.92-.83-1.97-1.71-2.41-1.71-.79,0-2.32,1.53-3.81,1.53s-2.32-1.53-2.32-1.53l-.22-1.84,3.64-2.28.13-4.25s1.49.31,3.55.83c2.06.57,1.93-1.49,1.93-2.85s-1.93-1.67-1.93-1.67l-.26-3.94-1.93.53.31-5.74s-3.59,0-5.35-.83c-1.8-.83-3.42-2.89-3.42-2.89l-4.95.18s-.13.48-.53,1.14Z"
          ></path>
        <path
          class="cls-2"
          d="m1082.95,603.65l2.5,9.69c-1.88,0-3.9.26-6.05.61-5.48.88-7.85,2.02-6.18,3.46,1.62,1.45,8.02,6.18,2.37,8.59-5.7,2.37-6.57,5.08-8.24,5.08-1.4,0-5.79-.13-7.1-1.8l3.9-7.89.57-9.82-3.37-1.23c.26-.75.44-1.45.61-2.1.18-.75.61-1.88,1.18-3.33l3.46.22c-.57,1.62-.44,3.29,1.67,3.94,4.38,1.36,4.95.57,14.68-5.44Z"
          ></path>
        <path
          class="cls-2"
          d="m1071.95,676.54l-66.67-.53v-46.9l-.92-.92-1.27-3.11,1.62-2.76-.18-3.81,3.51-4.87c11.75,4.65,23.23,5.87,23.23,5.87l10.45-3.11,9.27.62,6.44-.61s2.32,10.34,2.41,11.97c.04.35.18.66.39.92l-.75,1.45.22,8.33c-3.99.18-5.92-.61-7.06-3.11-1.36-3.02-8.24-10.69-4.69-2.19,3.59,8.5,6.05,10.69,10.43,18.06,3.51,5.87,9.73,15.43,13.54,24.72Z"
          ></path>
        <path
          class="cls-2"
          d="m1069.63,595.1c1.4,1.14,1.1,5.22-.26,6.05-.7.44-2.15,2.19-2.76,3.99l-3.46-.22c1.05-2.72,2.54-6.44,3.73-10.04,1.05-.18,2.19-.22,2.76.22Z"
          ></path>
        <path
          class="cls-2"
          d="m1064.72,611.58l-.57,9.82-3.9,7.89c-.22-.26-.35-.57-.39-.92-.09-1.62-1.4-7.63-2.41-11.97,1.97-1.36,3.16-3.81,3.9-6.05l3.37,1.23Z"
          ></path>
        <path
          class="cls-2"
          d="m1059.99,588.61s.13,1.14-.18,1.62c-.31.48-.79.83-1.23,1.18-1.53,1.14-3.07,2.24-4.65,3.29-.26.13-.79.39-.79.39,0,0-1.14.26-1.75.31-1.1,0-2.28-.09-3.2-.66-.96-.57-1.01-2.85-1.01-2.85,0,0,1.84-1.23,3.02-1.31,1.36-.09,2.76-.18,4.16-.26.57-.04,1.18-.09,1.75-.31.66-.26,1.23-.75,1.84-1.1.61-.35,2.02-.31,2.02-.31Z"
          ></path>
        <path
          class="cls-2"
          d="m1033.21,505.42c0,1.36.13,3.42-1.93,2.85-2.06-.53-3.55-.83-3.55-.83l-.13,4.25-3.64,2.28-1.01-9.51s-2.19-4.95-2.76-5.79c-.35-.57-3.33-4.3-5.04-6.49.39-.66.53-1.14.53-1.14l4.95-.18s1.62,2.06,3.42,2.89c1.75.83,5.35.83,5.35.83l-.31,5.74,1.93-.53.26,3.94s1.93.26,1.93,1.67Z"
          ></path>
        <path
          class="cls-2"
          d="m1013.39,544.21l-2.1,1.05-1.36,1.93h-3.86l-2.85-.96-5.22-.26-4.51,1.75-.44.18.53-5.74-2.02-.35v-1.27l-.96-.09.22-.48,1.67-4.91,2.19-2.59-1.49-.92-3.24-1.97,2.19-.22.35-2.19,1.27-1.1.13.04,1.36,3.11,12.49,1.1s4.91-4.08,6.57-4.21c1.27-.13,7.89,2.28,10.87,3.42-.75,1.4-1.58,3.11-2.19,5.7-1.18,4.78-.7,6.14.48,7.98h-4.12l-2.19-.83-3.77,1.84Z"
          ></path>
        <path
          class="cls-2"
          d="m1013.44,591.77c.18.44-.09,1.01-.48,1.27-.44.31-.92.35-1.4.39-.88.09-1.75.09-2.63.09-3.42-.13-6.84-.96-9.95-2.41-.26-.13-.57-.26-.75-.53-.18-.22-.22-.61-.04-.83.13-.13.31-.18.48-.26,2.15-.61,4.47-.22,6.71.22,1.4.26,2.85.57,4.25.83.83.13,1.62.31,2.45.44.53.13,1.14.31,1.36.79Z"
          ></path>
        <path
          class="cls-2"
          d="m919.16,624.73c1.62-1.53,4.3-4.03,4.3-4.03l-.18-5.65,7.28-4.78-.26-5.83c5.61,2.28,21.53,5.75,22.09,7.41.31,1.02,3.99,5.56,3.99,5.56,0,0,6.11,1.72,6.71,1.8.93.14,8.39,2.96,11.94,3.79,2.05.6,2.92-.03,3.4-6.77l1.24-11.13s9.03.37,15.46,3.16c4.65,2.02,8.99,3.86,12.93,5.39l-3.51,4.87.18,3.81-1.62,2.76,1.27,3.11.92.92v58.78h-5.87l.04,2.98c-9.55-5.26-40.67-22.13-43.22-22.62-1.58-.26-4.12.92-6.4,2.06-2.15,1.18-4.03,2.32-4.56,2.32-1.1,0-3.94-3.73-5.39-4.08-1.49-.39-7.14-1.14-7.14-1.14,0,0-.04-.04-.09-.13-.39-.79-2.67-5.13-3.2-5.3-.53-.22-7.67-2.94-7.67-2.94l-3.46-9.34,2.37-1.8-.18-16.61s-2.89-4.78-2.54-5.3c.09-.18.57-.66,1.18-1.27Z"
          ></path>
        <path
          class="cls-2"
          d="m972.02,520.06l1.67-2.72-2.02-1.14.09-4.21v-.04c1.23-.88,2.28-1.75,2.28-1.75,0,0,2.32-.35,5.35-.39l2.06,2.59.13,3.29,3.99,1.67-.57,3.42,2.32,2.02,1.49.44,2.76-1.93.83.83-.26,3.42,1.62.53-1.27,1.1-.35,2.19-2.19.22,3.24,1.97,1.49.92-2.19,2.59-1.67,4.91-.22.48-3.99-.31-.18,1.49-3.07-.18-2.72,1.27-.04-.39-.92-2.54-1.84-1.45,2.02-2.59-2.37-1.27-4.03-3.46s-.53-2.94-.35-3.46c.18-.57,1.67-.39,1.67-.39l-2.94-3.07,1.1-.92,1.1-1.45-2.02-1.67Z"
          ></path>
        <path
          class="cls-2"
          d="m992.93,430.73l.83,2.63-1.23,1.49.26,2.85-16.22-.79c.88-.88,1.01-1.93,1.1-2.85.18-1.67,2.59-2.41,3.29-2.41.75,0,1.58-.61,1.58-.61,1.84-.22,1.8,0,1.4-2.54l2.02.22,3.42,2.32,3.55-.31Z"
          ></path>
        <polygon
          class="cls-2"
          points="990.6 540.44 991.57 540.53 991.57 541.8 993.58 542.15 993.06 547.89 983.33 551.71 980.61 548.55 980.96 545.26 980.65 542.72 983.37 541.45 986.44 541.63 986.61 540.14 990.6 540.44"
          ></polygon>
        <path
          class="cls-2"
          d="m980.65,542.72l.31,2.54-.35,3.29,2.72,3.16-.39.13-2.32,3.81-5.92,3.99c-.13-1.14-.18-2.32-.22-3.59-.09-2.41,0-4.95.13-7.23.18-3.16-.26-5.39-1.1-7.06.53-.96,1.01-1.93,1.1-2.32.18-.92,3.24-1.1,3.24-1.1l1.84,1.45.92,2.54.04.39Z"
          ></path>
        <path
          class="cls-2"
          d="m979.86,535.75l-2.02,2.59s-3.07.18-3.24,1.1c-.09.39-.57,1.36-1.1,2.32-1.1-2.15-2.81-3.29-4.6-4.08.35-1.58.92-3.55,1.49-4.82,1.1-2.37,3.07-1.84,3.07-1.84l4.03,3.46,2.37,1.27Z"
          ></path>
        <path
          class="cls-2"
          d="m971.84,524.09l2.94,3.07s-1.49-.18-1.67.39c-.18.53.35,3.46.35,3.46,0,0-1.97-.53-3.07,1.84-.57,1.27-1.14,3.24-1.49,4.82-2.32-1.01-4.73-1.45-6.09-2.72,0-1.18-.18-2.85-1.01-4.12-1.49-2.19-8.24-9.86-8.24-9.86v-3.11s1.67,2.02,3.11,1.84c1.45-.18,2.76-1.84,2.76-1.84h5.48l2.54.53,4.56,1.67,2.02,1.67-1.1,1.45-1.1.92Z"
          ></path>
        <path
          class="cls-2"
          d="m937.57,422.32c.48,1.97-1.18,1.58-1.71,2.41-.53.92-.7,2.76-.53,5.3.18,2.54-1.84,4.73-3.29,5.65-1.49.92-2.41-.35-3.11-1.62-.75-1.32.7-1.49,1.84-.92,1.05.53,1.8-1.49,1.8-2.41s-1.45-2.19-3.46-2.37c-.35-.04-.61-.18-.75-.35-.66-.75.48-2.63,0-3.86-.53-1.45,1.27-4.38,2.94-4.91,0,0,1.1-1.1,2.72-1.1s2.19.75,3.33,3.46c.09.26.18.53.22.7Z"
          ></path>
        <path
          class="cls-2"
          d="m888.61,693.06l-5.52.96v-4.38l-6.57-2.76-6.57-5.74-30.68-23.27-1.27-.75-21.61-12.93-.04-3.59-.09-6.31,8.77-5.17,8.77.53,7.67-7.41,3.86.31.26-3.59-2.76-1.1v-5.22l15.34-.79v-1.1l1.93-1.36-4.65-4.12.53-10.43s-2.1-2.19-4.38-3.81c8.24-1.84,32.35-10.12,32.35-10.12,0,0,23.54-3.11,30.94-3.73l-2.76,3.99-.26,6.57s1.4,4.38.26,6c-1.05,1.67-4.65,3.86-4.65,5.22s1.67,8.5,3.29,9.6c1.67,1.1,5.74,3.02,5.74,3.02l2.67,13.15c-.61.61-1.1,1.1-1.18,1.27-.35.53,2.54,5.3,2.54,5.3l.18,16.61-2.37,1.8,3.46,9.34s7.14,2.72,7.67,2.94c.53.18,2.81,4.51,3.2,5.3-7.58,4.69-19.86,12.19-21.92,13.28-3.02,1.67-13.15,10.96-13.15,10.96l-8.99,1.53Z"
          ></path>
        <path
          class="cls-2"
          d="m930.29,604.44l.26,5.83-7.28,4.78.18,5.65s-2.67,2.5-4.3,4.03l-2.67-13.15s-4.08-1.93-5.74-3.02c-1.62-1.1-3.29-8.24-3.29-9.6s3.59-3.55,4.65-5.22c1.14-1.62-.26-6-.26-6l.26-6.57,2.76-3.99c3.02-.26,5.26-.39,6.31-.39h4.75l1.52,10.12,2.19,17.27c.21.1.44.22.66.26Z"
          ></path>
        <polygon
          class="cls-2"
          points="918.19 498.89 918.5 502.35 919.6 502.35 920.69 503.8 923.45 503.8 924.29 504.5 923.63 504.55 923.28 506.39 921.79 506.39 921.09 509.45 917.05 507.66 915.78 512.22 912.67 507.44 909.56 511.47 904.47 511.82 903.55 507.26 898.6 509.63 900.27 503.98 904.47 501.61 903.91 498.5 907.54 499.07 910.48 498.32 915.43 497.8 918.15 498.15 918.19 498.89"
          ></polygon>
        <path
          :class="['cls-2 bel', this.countries.includes('bel') ? 'hl' : null, this.focus == 'bel' ? 'focus' : null ]"
          d="m899.7,472.37l1.27,2.41-.83,2.15-2.81,1.31.26,3.68-1.01-.04-2.89-1.27-1.49-4.73-1.45,2.37-1.62-.18-.39-3.51-3.81-.18-.92-3.64-2.76-.57-1.53-2.28c1.53-.66,3.16-1.4,4.34-2.28l2.5,1.49,2.19-1.1.57-.92,4.91.7,2.37.57,1.32,1.45-.57,2.76,2.37,1.75v.04Z"
          ></path>
        <path
          class="cls-2"
          d="m882.95,557.58c1.84.39,2.94,4.82,0,4.82s-5.08-2.19-3.99-3.29c0,0,2.15-1.88,3.99-1.53Z"
          ></path>
        <path
          class="cls-2"
          d="m860.07,609.39l-1.93,1.36v1.1l-15.34.79v5.22l2.76,1.1-.26,3.59-3.86-.31-7.67,7.41-8.77-.53-8.77,5.17.09,6.31h-22.53c5.79-4.16,16.83-10.48,17.23-14.51.41-3.79,5.22-18.92,5.22-18.92l8.77-6.55,3.11-2.13,2.63-5.78s1.6-5.8,1.67-5.81c.56-.05,1.86.44,1.86.44,0,0,6.52,4.45,13.48,4.21,1.23-.04,2.5-.22,3.81-.53,2.28,1.62,4.38,3.81,4.38,3.81l-.53,10.43,4.65,4.12Z"
          ></path>
        <path
          class="cls-2"
          d="m829.96,440.82l1.27.39c-.22.57-.35,1.31-.22,2.32.75,6.22-.88,14.42-3.81,14.42s-9.12,6.22-15.69,6.97c-6.57.7-.75-10.26-.39-13.54.39-3.29-.88-10.04-2.02-12.23-1.05-2.19,1.31-1.27,7.49-1.62,3.77-.22,3.77-1.67,3.2-3.24-.61-1.71.26-3.59,2.02-4.08,1.14-.35,2.67-.79,4.25-.92l-2.15,3.86-2.72,2.72-.22,2.19,2.19,2.02,3.11-3.11,1.84,3.86h1.84Z"
          ></path>
        <g>
          <path
            class="cls-2"
            d="m870.46,450.85c3.11-.18,7.49,4.21,4.6,7.49-2.94,3.29-7.49,6.18-5.48,7.1,2.02.92,2.54,2.76,2.54,2.76,0,0-10.43,4.38-13.5,3.99-3.11-.35-11.88-1.1-12.27.75-.35,1.84-3.64,3.29-3.64,3.29,0,0-3.46-.18-4.91.92-1.49,1.1-3.46-1.45-3.46-1.45,0,0,5.08-8.24,8.2-8.42,3.11-.18,9.29-.92,7.32-1.84-2.02-.92-6.57-.53-7.49-1.27-.92-.75-5.13-1.62-5.13-1.62,0,0,.74-3.51,2.76-4.21,1.97-.75,3.99-5.3,2.37-6.22-1.67-.92-1.45-4.73-1.45-4.73,0,0,6.53,2.19,7.28-.39.75-2.54,1.45-6.36-.53-7.49,0,0-3.51-2.72-2.76-3.24.75-.57,2.94-4.03,1.27-4.03s-6.93,1.45-6.93,1.45c0,0-2.37-2.02-1.45-3.99.92-2.02,1.97-5.3.53-5.3s-2.28,3.11-3.46,3.29c-.83.09-1.45-1.49-1.45-2.94s-2.1-.26-2.59-.75c-.79-.79.75-2.72,2.37-3.81,1.67-1.1-.18-1.71-1.45-1.67-1.53.04-1.67-.75-.31-2.54s2.19-4.25,1.23-4.78c-.96-.57-5.35-2.37-4.25-4.25,1.1-1.93,3.42-3.86,3.29-2.06-.13,1.75.7,2.06,1.49.7.83-1.4,2.02-3.86,2.02-3.86,1.1-2.72-.88-6.4,1.67-6.75,2.54-.35,14.07-1.84,12.4.92-1.62,2.72-5.48,6.57-5.48,7.67s-.35,1.27,3.29.53c3.64-.7,8.77,1.49,8.77,1.49,0,0-5.65,10.56-6,12.75-.39,2.19-.92,6.4,1.1,7.49,1.97,1.1,8.37,8.02,8.94,8.77.53.75,4.56,2.94,4.56,2.94,0,0,.57,6.75,1.62,7.49,1.14.7.75,2.72,1.49,4.38.7,1.62-.18,1.62,2.89,1.45Z"
            ></path>
          <path
            class="cls-2"
            d="m831.94,431.3c5.22,8.11.53,6.84-.7,9.91l-1.27-.39h-1.84l-1.84-3.86-3.11,3.11-2.19-2.02.22-2.19,2.72-2.72,2.15-3.86c2.28-.26,4.6.04,5.87,2.02Z"
            ></path>
          <path
            class="cls-2"
            d="m831.58,397.47c.09.44-.22.88-.44,1.27-.61,1.05-.53,2.37-.96,3.51-.04.18-.13.35-.31.53-.26.22-.7.22-1.05.18-.96-.04-2.1-.26-2.41-1.14-.04-.22-.04-.44-.04-.66-.04-.88.04-1.75.35-2.54.35-.79.96-1.49,1.75-1.75.53-.18,1.05-.13,1.58-.13.61,0,1.4.13,1.53.75Z"
            ></path>
          <path
            class="cls-2"
            d="m826.32,405.01c.09.88-.83,2.1-1.18,2.85-.13.26-.26.57-.53.7-.44.22-.96-.09-1.23-.53-.48-.92-.48-2.32,0-3.16.26-.44.75-1.32,1.62-1.05.88.31,1.31,1.18,1.31,1.18Z"
            ></path>
        </g>
        <path
          class="cls-2"
          d="m1034.85,233.8c-1.88-.57-13.41-5.74-16.13-5.74s-13.41,1.62-18.1,4.38c-4.65,2.72-11.48,6.01-22.18,9.03-10.69,3.02-18.63,18.06-20.82,23.27-1.8,4.25-3.9,8.46-7.01,14.77-.7,1.45-1.45,2.98-2.28,4.69-1.67,3.38-5.08,9.99-8.94,17.27-6.44,12.14-14.2,26.21-17.09,30.68-4.65,7.1-17.27,13.67-17.27,13.67-8.5,7.67-11.79,10.43-10.43,13.46,1.4,2.98.57,17.53.83,30.11.31,12.58,13.98,11.53,17.01,9.6,3.02-1.93,6.57-6.05,11.79-11.22,3.33-3.38,4.08-.44,4.51,3.02l1.14-.31,1.8-9.12c2.59-1.1,4.38-8.77,2.94-12.45-1.45-3.64.35-2.54.35-2.54,0,0,3.29-2.19,0-5.13-3.29-2.89-1.8-24.81-1.8-24.81l3.99-5.87,7.32.75-2.19-9.86,4.03-6.57-.39-12.05,5.87-2.19.35-4.38s5.48-4.73,4.73-7.67c-.53-2.28-.92-6.09-.53-7.85.13-.48.31-.83.53-.92,1.1-.35,2.94-5.83,5.48-5.48,2.59.35,5.48,0,4.78-4.38l-.75-4.38,10.61,4.03s1.8-6.57,1.1-7.67c-.75-1.1,1.1-1.84,1.1-1.84l1.75-.79,2.24-1.05,3.68-2.54s2.54,8.42,3.99,8.77c1.49.35,7.67-1.1,7.67-1.1l5.87,4.38,2.19-5.13s4.38-.35,3.64-5.48c-.75-5.08,4.03-12.05,4.03-12.05l2.54.39,5.83-2.94,1.49,4.73,3.99,1.49s.75,4.73-.61,8.28c-.57,1.53-.88,3.07-1.05,4.3l2.41-1.27,1.36-4.12,4.12-1.88v-3.59l2.19,1.4h2.45l-.13-2.67v-.04c-2.59-1.45-4.56-2.76-5.35-3.33-2.19-1.67,1.36-4.12,5.48-5.74,4.12-1.67-2.19-5.74-4.12-6.31Z"
          ></path>
        <path
          id="malta"
          class="cls-2"
          d="m949.15,587.61h-.04s-1.44-.45-1.44-.45h-.04s0-.05,0-.05l-.18-1.84v-.14s.1.08.1.08l.7.52,1.66.87.07.04-.05.06-.74.88-.03.03Z"
          ></path>
        <path
          id="islanda"
          class="cls-2"
          d="m789.62,314.54c-.75,4.73-.75,9.47-7.67,12.75-6.97,3.29-17.53,14.64-21.56,13.15-4.03-1.45-8.02-4.38-11.31-5.08-3.29-.75-12.45.7-12.05-1.1.35-1.84,4.73-3.68,4.73-5.87s.75-6.57-3.64-6.57-12.8-2.54-6.97-3.29c5.87-.7,10.96-2.54,9.51-4.38-1.45-1.8-6.57-.7-8.42-.7s-5.83,1.1-2.89-4.38c2.89-5.48,5.83-9.51,7.28-10.26,1.49-.7,6.57.39,7.32,4.03s5.13,11.7,5.83,6.57c.75-5.13,2.19-8.42,3.68-5.48,1.45,2.94-.39,5.13,2.54.75,2.94-4.38,5.13-4.78,8.02-2.94,2.94,1.84,5.87,4.38,5.87,1.1s2.19-8.02,4.73-6.22c2.54,1.84,5.83,2.94,8.42,5.87,2.54,2.89,6.57,12.05,6.57,12.05Z"
          ></path>

        <!-- COUNTRIES USATE PER highlights -->

        <path
          :class="['cls-2 fin', this.countries.includes('fin') ? 'hl' : null, this.focus == 'fin' ? 'focus' : null ]"
          d="m1026.41,261.64c-.13,1.67-.04,2.85-.04,2.85l-.83,8.46s4.12,1.67,6.31,4.12.26,6.57,0,7.67c-.26,1.1-3.86,5.74-3.86,6.57s6.31,17.53,6.31,17.53l-2.45.57-.57,6.57,1.36,1.1-1.62,1.88.83,1.93h2.19l.26,6.57,2.45,2.76-2.98,4.08s10.65,6.88,8.2,11.53c-1.97,3.68-15.52,20.73-20.99,27.57-1.4.13-3.11.48-5.3,1.18-9.34,3.02-15.08,9.6-18.89,7.67-3.86-1.93-9.86-4.65-10.17-10.39-.26-5.74.31-14.25-.79-18.37-1.1-4.12-3.59-7.93.79-11.48,4.38-3.59,12.89-15.08,15.91-17.84,3.02-2.72,10.12-7.67,4.65-11.79-2.37-1.8-5.04-3.68-7.5-4.91l-2.1-6.57,1.67-5.48v-2.19l-1.67-4.38.83-3.29s-2.19-1.1-1.62-2.72c.53-1.67,0-7.14,1.1-7.98,1.1-.79-6.57-5.17-7.41-5.17s-4.38-3.33-6.05-5.22c-.88-1.05-2.37-3.2-3.51-4.91l2.24-1.05,3.68-2.54s2.54,8.42,3.99,8.77c1.49.35,7.67-1.1,7.67-1.1l5.87,4.38,2.19-5.13s4.38-.35,3.64-5.48c-.75-5.08,4.03-12.05,4.03-12.05l2.54.39,5.83-2.94,1.49,4.73,3.99,1.49s.75,4.73-.61,8.28c-.57,1.53-.88,3.07-1.05,4.3Z"
        ></path>
        <path
          :class="['cls-2 bgr', this.countries.includes('bgr') ? 'hl' : null, this.focus == 'bgr' ? 'focus' : null ]"
          d="m993.76,526.07l-1.62-.53.26-3.42-.83-.83-2.76,1.93-1.49-.44-2.32-2.02.57-3.42-3.99-1.67-.13-3.29-2.06-2.59h.53c3.29,0,3.29-1.1,4.82-1.8,1.49-.7,2.85-7.54,3.68-8.5.83-.96,4.38-3.94,4.38-3.94l3.16-1.8,1.36,1.1h5.92s1.1,2.06,2.32,1.93c1.23-.13,2.72-1.36,2.72-1.36,0,0,2.63.13,4.65-.96,1.1-.61,1.84-1.53,2.24-2.28,1.71,2.19,4.69,5.92,5.04,6.49.57.83,2.76,5.79,2.76,5.79l1.01,9.51.22,1.84s.83,1.53,2.32,1.53,3.02-1.53,3.81-1.53c.44,0,1.49.88,2.41,1.71-.18.39-.39.88-.61,1.45-1.27,3.29-4.95,3.81-5.3,6.57-.18,1.4-.83,2.5-1.62,3.99-2.98-1.14-9.6-3.55-10.87-3.42-1.67.13-6.57,4.21-6.57,4.21l-12.49-1.1-1.36-3.11-.13-.04Z"
        ></path>
        <path
          :class="['cls-2 ltu', this.countries.includes('ltu') ? 'hl' : null, this.focus == 'ltu' ? 'focus' : null ]"
          d="m1022.82,384.76l1.05,2.15s-4.08,3.59-4.38,5.22c-.26,1.67,1.67,8.77,1.67,8.77l-2.06,5.44-1.8.31-.66-1.49-2.59,1.49-6.75-6.27-4.51,1.62c.09-.75.04-1.32,0-1.62-.26-1.67-4.65-1.67-5.22-5.74-.53-4.12.83-7.71,4.12-8.5,3.29-.83,11.79-1.4,17.53-.83,1.4.13,2.59-.09,3.59-.53Z"
        ></path>
        <path
          :class="['cls-2 lva', this.countries.includes('lva') ? 'hl' : null, this.focus == 'lva' ? 'focus' : null ]"
          d="m1022.82,412.68l.61,7.71-.09-.04-3.64,3.46-2.19-.92-2.94,1.67-.04.22-4.73-4.82-4.38-.44-.13-2.45-4.12,2.45-5.92-1.1-5.87-1.36-4.95,3.86-1.14-.09c-.04-7.36,2.41-12.14,3.64-13.63,1.36-1.62,5.48-3.55,7.93-.26,2.45,3.29,4.12,4.38,5.74,3.81,1.36-.39,2.1-5.83,2.19-8.77l4.51-1.62,6.75,6.27,2.59-1.49.66,1.49,1.8-.31-.13.31,1.67,1.67-.83,5.22,3.02-.83Z"
        ></path>
        <path
          :class="['cls-2 est', this.countries.includes('est') ? 'hl' : null, this.focus == 'est' ? 'focus' : null ]"
          d="m1013.66,428.19l1.1,1.27-5.3,3.46s-1.1,4.78-1.1,5.87-4.21,2.54-5.83,3.11c-1.62.53-5.13.18-5.13.18l-3.24-4.34-1.36-.04-.26-2.85,1.23-1.49-.83-2.63-3.55.31-3.42-2.32-2.02-.22c-.18-1.18-.39-2.98-.57-5.7-.04-.7-.09-1.36-.09-1.97l1.14.09,4.95-3.86,5.87,1.36,5.92,1.1,4.12-2.45.13,2.45,4.38.44,4.73,4.82-.88,3.42Z"
        ></path>
        <path
          :class="['cls-2 grc', this.countries.includes('grc') ? 'hl' : null, this.focus == 'grc' ? 'focus' : null ]"
          d="m983.33,551.71l9.73-3.81.44-.18,4.51-1.75,5.22.26,2.85.96h3.86l1.36-1.93,2.1-1.05,1.31,3.24-1.23,2.19-2.81,2.81c-.75-.53-1.67-.88-2.85-.96-4.21-.39-9.12.18-8.24,1.45.48.67-.11,1.89-.11,1.89,0,0-1.31.74-2.43.66-2.37-.18-5.3-2.72-3.64,1.67,1.62,4.38,5.08,8.42,6.57,9.47,1.08.85,3.96,3.73,3.96,3.73,0,0-.37.95-1.24,1.4-3.46,1.84-5.3,1.45-6.57.75-1.27-.75-1.62,0-.53,1.1,1.1,1.1-.57,3.99-.57,3.99l-.18,5.13s-6.05-1.45-7.67-4.38c-1.62-2.94-3.11-6.93-3.11-6.93l3.29-1.27-2.54-1.1-3.11-4.03-3.98.51-2.07-1.25s-.79-2.72-.96-4.6l5.92-3.99,2.32-3.81.39-.13Z"
        ></path>
        <path
          :class="['cls-2 pol', this.countries.includes('pol') ? 'hl' : null, this.focus == 'pol' ? 'focus' : null ]"
          @click="this.$emit('country', 'poland')"
          d="m992.79,437.7l1.36.04,3.24,4.34s.18,3.29.39,3.99c.18.75,1.8,5.52,1.62,6.22-.18.75-2.72,2.94-2.72,2.94l-1.49,2.54,2.37,1.67.22,5.65,1.71,1.27-.39,1.62,1.62.44-.26,5.87-2.59.13-5.48,7.54.96,3.29s-.26.22-.66.48c-1.67-.44-4.08-1.27-4.08-1.27l-2.02-1.49-2.72.18s-1.45,1.49-2.94.57c-1.45-.92-4.91,1.1-4.91,1.1l-1.84-3.68-3.64,1.31-.04-.18-.53-4.03-6.18-1.67s.35-2.54-1.31-2.37c-1.62.18-2.54,4.38-3.46,3.11s-2.37-4.95-3.11-5.83c-.7-.92-5.65-1.1-5.65-1.1,0,0-.53-.61-1.1-1.05v-4.25l-1.8-2.02-.22-8.59-2.72-2.02,1.67-3.64.88-2.02-1.62-.75v-4.82c1.93.61,3.9.61,5.48-.44,1.62-1.1,9.69-6.4,12.23-6.97,2.54-.53,5.48-1.1,6,.39.57,1.45-.18,5.48,4.03,4.38,1.75-.44,2.81-1.05,3.46-1.71l16.22.79Z"
        ></path>
        <path
          :class="['cls-2 swe', this.countries.includes('swe') ? 'hl' : null, this.focus == 'swe' ? 'focus' : null ]"
          d="m997.57,300.91l2.1,6.57c-3.2-1.62-6.14-2.19-7.85,0-3.02,3.86-5.74,10.69-6.57,15.08-.83,4.38-3.02,10.69-9.29,16.13-6.31,5.52-13.72,17.84-13.98,23.84-.26,6.05,3.02,8.77,6.05,11.53,2.98,2.72,7.1,12.58,1.36,15.6-5.74,3.02-9.86,7.67-9.86,11.79s1.1,16.7-4.95,18.89c-6,2.19-6.57,7.41-10.96,7.41-2.76,0-4.3-2.28-5.35-5.65-.61-1.97-1.05-4.43-1.49-6.97-1.1-6.84-5.74-15.34-7.14-18.89-.48-1.27-.66-3.29-.92-5.17l1.14-.31,1.8-9.12c2.59-1.1,4.38-8.77,2.94-12.45-1.45-3.64.35-2.54.35-2.54,0,0,3.29-2.19,0-5.13-3.29-2.89-1.8-24.81-1.8-24.81l3.99-5.87,7.32.75-2.19-9.86,4.03-6.57-.39-12.05,5.87-2.19.35-4.38s5.48-4.73,4.73-7.67c-.53-2.28-.92-6.09-.53-7.85.13-.48.31-.83.53-.92,1.1-.35,2.94-5.83,5.48-5.48,2.59.35,5.48,0,4.78-4.38l-.75-4.38,10.61,4.03s1.8-6.57,1.1-7.67c-.75-1.1,1.1-1.84,1.1-1.84l1.75-.79c1.14,1.71,2.63,3.86,3.51,4.91,1.67,1.88,5.22,5.22,6.05,5.22s8.5,4.38,7.41,5.17c-1.1.83-.57,6.31-1.1,7.98-.57,1.62,1.62,2.72,1.62,2.72l-.83,3.29,1.67,4.38v2.19l-1.67,5.48Z"
        ></path>
        <path
          :class="['cls-2 hun', this.countries.includes('hun') ? 'hl' : null, this.focus == 'hun' ? 'focus' : null ]"
          @click="this.$emit('country', 'hungary')"
          d="m959.04,507.66c-1.53-1.45-3.64-3.33-3.64-3.33l2.45-1.1.13-4.82,3.16-.66.44-3.29,5.61,2.59,3.55-.57.13-2.72,3.99.7.13-1.4,3.02.44,3.55-3.42,2.06.96,5.61.09v.04l3.55,4.38s-3.55,2.98-4.38,3.94c-.83.96-2.19,7.8-3.68,8.5-1.53.7-1.53,1.8-4.82,1.8h-.53c-3.02.04-5.35.39-5.35.39,0,0-1.05.88-2.28,1.75v.04c-1.23.83-2.63,1.75-3.2,1.75-1.1,0-7.8-3.81-7.93-4.38-.04-.18-.7-.88-1.58-1.71Z"
        ></path>
        <path
          :class="['cls-2 svk', this.countries.includes('svk') ? 'hl' : null, this.focus == 'svk' ? 'focus' : null ]"
          @click="this.$emit('country', 'slovakia')"
          d="m988.63,484.47s2.41.83,4.08,1.27c-.53.44-1.23.92-1.53.92-.53,0-1.75,3.9-1.93,4.47l-5.61-.09-2.06-.96-3.55,3.42-3.02-.44-.13,1.4-3.99-.7-.13,2.72-3.55.57-5.61-2.59-1.45-1.62-.13-3.77,2.72-1.88h3.46v-2.94l1.84-.7,1.8-.57.7-.7.04.18,3.64-1.31,1.84,3.68s3.46-2.02,4.91-1.1c1.49.92,2.94-.57,2.94-.57l2.72-.18,2.02,1.49Z"
        ></path>
        <path
          :class="['cls-2 hrv', this.countries.includes('hrv') ? 'hl' : null, this.focus == 'hrv' ? 'focus' : null ]"
          d="m973.68,517.34l-1.67,2.72-4.56-1.67-2.54-.53h-5.48s-1.32,1.67-2.76,1.84c-1.45.18-3.11-1.84-3.11-1.84v3.11s6.75,7.67,8.24,9.86c.83,1.27,1.01,2.94,1.01,4.12-.13-.04-.22-.18-.31-.26-3.94-4.51-9.82-7.1-9.82-7.1l-3.46-7.14-2.41-2.63-1.67,1.97-3.29-2.89s.04-.96.13-1.4l4.78-.09.39-1.4,2.5,1.4,1.1.13,1.23-3.02,1.23-.13-.13-2.59,3.42-1.1,2.54-1.05c.88.83,1.53,1.53,1.58,1.71.13.57,6.84,4.38,7.93,4.38.57,0,1.97-.92,3.2-1.75l-.09,4.21,2.02,1.14Z"
        ></path>
        <path
          :class="['cls-2 cze', this.countries.includes('cze') ? 'hl' : null, this.focus == 'cze' ? 'focus' : null ]"
          @click="this.$emit('country', 'czech_rep')"
          d="m944.32,489.29l-10.3-8.85s1.67-1.67.92-2.76c-.7-1.1-1.8-2.37-1.8-2.37l12.4-6.57s2.02.18,2.76.18c.26,0,.57.18.88.44.57.44,1.1,1.05,1.1,1.05,0,0,4.95.18,5.65,1.1.75.88,2.19,4.56,3.11,5.83s1.84-2.94,3.46-3.11c1.67-.18,1.31,2.37,1.31,2.37l6.18,1.67.53,4.03-.7.7-1.8.57-1.84.7v2.94h-3.46l-2.72,1.88-.22.13-3.46.18-2.19-1.84-2.19-1.27-2.59-.92-1.27,3.29v1.84l-1.97.35-1.8-1.53Z"
        ></path>
        <path
          @click="this.$emit('country', 'austria')"
          :class="['cls-2 aut', this.countries.includes('aut') ? 'hl' : null, this.focus == 'aut' ? 'focus' : null ]"
          d="m960.14,492.84l1.45,1.62-.44,3.29-3.16.66-.13,4.82-2.45,1.1-.7.92-5.35.44s-.39,1.75-2.19,1.75-5.49-1.05-5.49-1.05l-.94-.25-2.71-.08-2.77-.6h-.85s0-2.93,0-2.93l-5.3.18-1.45,1.67-3.38.13-.83-.7h-2.76l-1.1-1.45h-1.1l-.31-3.46h2.15l1.27,1.8,1.84.18v-2.37l2.94.39,1.27,1.45,3.81-2.02,2.19-1.45,4.95,2.72-.57-4.56,1.84-3.46v-1.45l4.43-.83,1.8,1.53,1.97-.35v-1.84l1.27-3.29,2.59.92,2.19,1.27,2.19,1.84,3.46-.18.22-.13.13,3.77h.02Z"
        ></path>
        <path
          :class="['cls-2 svn', this.countries.includes('svn') ? 'hl' : null, this.focus == 'svn' ? 'focus' : null ]"
          @click="this.$emit('country', 'slovenia')"
          d="m959.04,507.66l-2.54,1.05-3.42,1.1.13,2.59-1.23.13-1.23,3.02-1.1-.13-2.5-1.4-.39,1.4-4.78.08s-.02-.36-.02-.36c0,0,.92-.12.92-.16,0-.04.26-.22.25-.26-.06-.2-.16-.47-.25-.71l-1.18-1.09-.56-.12-.24-.35.26-.95-.06-.25-.59.18-.26-.06-.14-.33.07-.26.97-.84.12-.21v-.2s-.45-.1-.45-.1l-.73-.31h-.21s-.16.11-.16.11l-.23-.11-.03-.91,2.07-1.31.2-.51s3.68,1.05,5.43,1.05,2.19-1.75,2.19-1.75l5.35-.44.7-.92s2.1,1.88,3.64,3.33h0Z"
        ></path>
        <path
          :class="['cls-2 deu', this.countries.includes('deu') ? 'hl' : null, this.focus == 'deu' ? 'focus' : null ]"
          @click="this.$emit('country', 'germany')"
          d="m900.14,476.93l.83-2.15-1.27-2.41v-2.37l-1.1-2.19,2.02-3.29-2.37-2.37,5.83-2.54-.35-5.48,1.62-.35.88-8.06c2.72-.61,8.24-3.33,8.24-3.33,0,0,.53-6.22.22-9.64l6.53.48c.61,1.88,1.8,4.47,3.33,4.47,2.19,0,4.03-.57,4.03-.57,0,0-1.84,5.48.7,4.38,2.54-1.1,11.88-5.83,11.88-5.83,0,0-1.27,2.37,1.45,4.21.88.57,1.84,1.05,2.76,1.36v4.82l1.62.75-.88,2.02-1.67,3.64,2.72,2.02.22,8.59,1.8,2.02v4.25c-.31-.26-.61-.44-.88-.44-.75,0-2.76-.18-2.76-.18l-12.4,6.57s1.1,1.27,1.8,2.37c.75,1.1-.92,2.76-.92,2.76l10.3,8.85-4.43.83v1.45l-1.84,3.46.57,4.56-4.95-2.72-2.19,1.45-3.81,2.02-1.27-1.45-2.94-.39v2.37l-1.84-.18-1.27-1.8h-2.15l-.04-.75-2.72-.35-4.95.53-2.94.75.57-6.57,3.29-6.22-6.4-.35-1.1-1.67-2.85-2.02.66-2.72-1.62-2.54.04-.04Z"
        ></path>
        <path
          :class="['cls-2 hol', this.countries.includes('hol') ? 'hl' : null, this.focus == 'hol' ? 'focus' : null ]"
          @click="this.$emit('country', 'holland')"
          d="m906.23,445.72l-.88,8.06-1.62.35.35,5.48-5.83,2.54,2.37,2.37-2.02,3.29,1.1,2.19v2.32l-2.37-1.75.57-2.76-1.32-1.45-2.37-.57-4.91-.7-.57.92-2.19,1.1-2.5-1.49c.39-.31.7-.57.96-.88,2.06-2.37,6.14-9.34,6.57-10.83.39-1.53,1.1-3.73,1.93-3.16.79.53.53,4.38,2.02,4.38s1.53-1.1,1.4-2.5c-.18-1.36-1.53-3.55-.18-4.65,1.4-1.1,6.05-1.36,7.98-1.93.35-.09.88-.22,1.49-.35Z"
          ></path>
        <polygon
          :class="['cls-2 lux', this.countries.includes('lux') ? 'hl' : null, this.focus == 'lux' ? 'focus' : null ]"
          @click="this.$emit('country', 'luxemburg')"
          points="900.09 476.98 901.71 479.52 901.06 482.24 900.79 482.06 897.59 481.93 897.33 478.25 900.14 476.93 900.09 476.98"
        ></polygon>
        <g id="italy" @click="this.$emit('country', 'italy')">
          <path
            :class="['cls-2 ita', this.countries.includes('ita') ? 'hl' : null, this.focus == 'ita' ? 'focus' : null ]"
            d="m961.85,554.45l5.74,4.69,1.97-2.94c0-.26-.01-.53-.04-.79-.13-1.23-13.16-8.64-13.16-8.64l-1.66-3.12s-3.42-.3-5.17-.96c-1.8-.7-7.26-13.05-7.26-13.05l-7.47-6.65.66-4.21-1.04-3.26,1.71-1.04,1.88-.63h.03s-.02-.03-.02-.03l-.21-.3.32-.24,1.88.57h.01s0,0,0,0c0,0,.17-.13.34-.26.3-.22.36-.26.37-.27h.38l1.24,1.21-.45.26-.03.32h.55s0,0,0,0h0s.41-.12.41-.12h0s0,0,0,0l.25-.26h0s0-.02,0-.02l-.25-.68h0s0,0,0,0l-1.18-1.09h0s0,0,0,0l-.55-.12-.24-.35.26-.95h0s0-.01,0-.01l-.06-.22v-.02s-.03,0-.03,0c0,0-.13.04-.26.08-.26.08-.28.09-.29.1,0,0,0,0-.01,0-.05,0-.2-.04-.26-.06-.04-.08-.13-.27-.14-.31,0-.01,0-.05.03-.16.02-.05.04-.1.04-.12l.97-.84h0s0,0,0,0c.03-.05.1-.18.11-.19,0,0,.01-.03,0-.11,0-.04,0-.08,0-.08h0s-.01-.02-.01-.02l-.44-.1-.72-.31h0s0,0,0,0h-.21s-.16.11-.16.11l-.23-.11-.03-.33v-.58l2.07-1.31h0s0-.01,0-.01l.18-.48v-.02s-.01,0-.01,0l-.93-.24h0s0,0,0,0l-2.63-.09-2.9-.6h-.81s0-2.94,0-2.94l-5.31.18-1.44,1.67-3.38.13-.66.04-.35,1.84h-1.49l-.7,3.07-4.03-1.8-1.27,4.56-3.11-4.78-3.11,4.03-5.09.35-1.31,1.14,1.67,3.24-2.02,2.77,1.45,1.84v4.74l3.86.18-.09,3.02,7.03-2.67,5.55.96,7.01,10.7.74.92,13.2,10.18s.46.35,1.22.95c.36.28,1.55.4,1.55.4l6.8,5.86s4.06,4.52,4.42,5.56c.96,2.72,0,5.61-1.23,7.54-.53.83-.64,1.96-.64,1.96,0,0,.41,1.68.77,1.73.19.02,2.38-1.23,2.38-1.23,0,0,2.18-2.27,2.92-3.72.9-1.82,2.14-4.99,2.14-4.99,0,0-.96-2.24-1.57-3.22-1.49-2.45,1.54-5.22,1.54-5.22Z"
          ></path>
          <polygon
            :class="['cls-2 ita', this.countries.includes('ita') ? 'hl' : null, this.focus == 'ita' ? 'focus' : null ]"
            points="952.25 570.47 952.96 570.55 953.21 571.08 952.82 571.83 951.42 575.38 951.62 579.33 951.55 579.76 950.84 580.5 948.71 580.42 947.34 579.76 943.92 577.56 939.1 575.81 936.87 574.98 935.05 573.75 936.44 571.24 940.2 570.85 943.46 571.62 945.54 571.83 948.07 571.4 952.25 570.47"
          ></polygon>
          <polygon
            :class="['cls-2 ita', this.countries.includes('ita') ? 'hl' : null, this.focus == 'ita' ? 'focus' : null ]"
            points="917.92 548.37 913.96 549.9 912.46 552.49 912.46 562.17 915.19 565.31 917.92 565.31 919.58 563.64 920.27 557.07 919.58 550.29 917.92 548.37"
          ></polygon>
        </g>
        <path
          :class="['cls-2 den', this.countries.includes('den') ? 'hl' : null, this.focus == 'den' ? 'focus' : null ]"
          d="m926.87,428.5c.09.35.13.66.04.96-.35,1.49-3.46,3.11-4.21,1.27-.7-1.8-1.27-3.24-2.02-3.24-.7,0,.18,3.07.18,3.99,0,.31.13.96.35,1.75l-6.53-.48c-.18-1.67-.39-3.02-.53-3.51-.39-1.49-2.85-4.51-2.85-4.51,0,0-.83-6.57,0-9.47.79-2.85,3.94-5.17,3.94-5.17l9.73-4.95s-2.19,8.24-1.36,9.03c.83.83,3.29,3.42,3.68,3.42,0,0-.75,2.94-1.49,4.38-.75,1.49-4.03,3.29-4.03,4.21s1.84-.18,2.76-.18c.7,0,2.02,1.23,2.32,2.5Z"
        ></path>
        <path
          :class="['cls-2 esp', this.countries.includes('esp') ? 'hl' : null, this.focus == 'esp' ? 'focus' : null ]"
          d="m884.14,539.13c.09,2.02-.79,4.65-.79,4.65l-6.31,4.78-8.33,4.78-4.85,8.8.9,5.02-3.46,6.47-13.15,7.54-11.79,3.55-3.07.22-3.2-3.38-6.79-3.9s.39-6.09.61-6.44c.35-.57.35-4.78.35-4.78,0,0,1.31-.53.92-1.8-.35-1.27-.18-2.41-.18-2.41l-2.19-2.19,3.29-.53,1.1-10.21,3.29-4.03-2.54-.18.35-2.19-8.94,1.27-.57-2.72-1.97.79c-.13-1.67-.31-3.07-.7-3.55-.96-1.1-1.67-4.38-1.67-4.38l11.66-4.25s24.37,1.8,26.56,1.67c.44-.04,1.05-.35,1.75-.96,1.62,1.84,4.3,4.25,4.3,4.25l8.33,2.32,5.22-.26s2.32,1.88,3.42,2.19c.7.18,5.22,0,8.46-.13Z"
        ></path>
        <path
          :class="['cls-2 prt', this.countries.includes('prt') ? 'hl' : null, this.focus == 'prt' ? 'focus' : null ]"
          d="m830.49,545.26l-3.29,4.03-1.1,10.21-3.29.53,2.19,2.19s-.18,1.14.18,2.41c.39,1.27-.92,1.8-.92,1.8,0,0,0,4.21-.35,4.78-.22.35-.48,3.9-.61,6.44-1.32-.09-7.06.68-7.06.68l-1.1-4.18s-3.55-8.9-2.32-10.96c1.23-2.02,5.04-10.96,4.51-13.68-.31-1.67-.35-4.78-.53-7.28l1.97-.79.57,2.72,8.94-1.27-.35,2.19,2.54.18Z"
        ></path>
        <g id="francia">
          <!-- FRANCIA -->
          <path
            :class="['cls-2 fra', this.countries.includes('fra') ? 'hl' : null, this.focus == 'fra' ? 'focus' : null ]"
            d="m901.06,482.24l2.85,2.02,1.1,1.67,6.4.35-3.29,6.22-.57,6.57-3.64-.57.57,3.11-4.21,2.37-1.67,5.65,4.95-2.37.92,4.56-1.31,1.14,1.67,3.24-2.02,2.76,1.45,1.84v4.73l3.86.18-.09,3.02s-.09.04-.13.09c-1.3,1.49-5.08,5.09-5.08,5.09l-3.02.39-12.31-2.94-2.59,1.84s-.79,4.25-.75,5.92c-3.24.13-7.76.31-8.46.13-1.1-.31-3.42-2.19-3.42-2.19l-5.22.26-8.33-2.32s-2.67-2.41-4.3-4.25c2.85-2.28,6.93-8.5,5.52-16.17-1.8-9.6-7.01-14.64-9.86-15.91-2.89-1.23-9.99-2.45-9.99-2.45l.53-7.23s10.96.39,13.15.53c2.19.13,3.99-1.36,3.55-2.45-.39-1.1.18-6.71.18-6.71,0,0,5.17,4.12,6.97,3.16,1.8-.96,5.61-5.08,7.8-6.57,2.19-1.53,1.53-6.31,3.55-7.41.88-.48,2.37-1.01,3.9-1.62l1.53,2.28,2.76.57.92,3.64,3.81.18.39,3.51,1.62.18,1.45-2.37,1.49,4.73,2.89,1.27,1.01.04,3.2.13.26.18Z"
          ></path>
          <!-- CORSICA -->
          <path
            :class="['cls-2 fra', this.countries.includes('fra') ? 'hl' : null, this.focus == 'fra' ? 'focus' : null ]"
            d="m919.64,538.78c.22.31.35.66.35,1.01,0,1.45-1.1,6.57-2.59,6.93-.18.04-.35.09-.53.09-1.18,0-2.1-1.18-2.76-3.73-.7-2.94,1.1-5.13,3.68-5.83,0,0,1.23.61,1.84,1.53Z"
          ></path>
        </g>
      </g>
    </svg>
  </div>
</template>

<script>
import gsap from 'gsap'

export default {
  name: "WorldSvg",
  props: {
    countries: Array,
    zoomlevel: String,
    focus: String,
    d: Number
  },
  beforeUpdate() {
    if(document.querySelector("#world_map .focus"))
      gsap.to('#world_map .focus', { fill: '#285b78' })
  },
  updated() {
    if(document.querySelector("#world_map .focus"))
      gsap.to('#world_map .focus', { fill: '#86a0ac' })

    //animazione opacità sfondo in caso sto andando in fvg
    if(this.zoomlevel=='zoom-fvg') {
      this.$refs.worldmap.classList.add('hide')
      setTimeout(() => {
        this.$refs.worldmap.classList.remove('hide')
      }, this.d*1000)
    }
  }
};
</script>

<style scoped>

.cls-2 {
  stroke: #0a3141;
  fill: #285b78;
  opacity: 0.7;
  transition: stroke-width 2000ms ease, opacity 2000ms ease, fill-opacity 1000ms ease, stroke 2000ms ease;
  /* transition: all 3000ms ease; */
  stroke-width: 0.05vw;
}
.cls-2.hl { opacity: 1; }

.zoom-global .cls-2 { 
  transition: stroke-width 2000ms ease, opacity 2000ms ease, fill-opacity 1000ms ease, stroke 2000ms ease;
  /* transition: all 3000ms ease; */
  stroke-width: 0.05vw;
}

.zoom-country .cls-2,
.zoom-europe .cls-2 {
  transition: stroke-width 2000ms ease, opacity 2000ms ease, fill-opacity 1000ms ease, stroke 2000ms ease;
  /* transition: all 3000ms ease; */
  stroke-width: 0.01vw;
}

.video-layer .cls-2,
.zoom-fvg .cls-2 {
  transition: stroke-width 2000ms ease, opacity 2000ms ease, fill-opacity 1000ms ease, stroke 2000ms ease;
  /* transition: all 3000ms ease; */
  stroke-width: 0.003vw;
  stroke: #fff;
  opacity: 1;
  fill-opacity: 0.7;
}

/* ------------------------------------------------------------ */
.map-wrapper svg {
  opacity: 1;
  transition: opacity 1500ms ease;
}

.map-wrapper svg.video-layer,
.map-wrapper svg.hide {
  opacity: 0;
  transition: opacity 1500ms ease;
}

.map-wrapper svg {
  background-image: url(../../assets/mappa_png.png);
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center center;
}
</style>