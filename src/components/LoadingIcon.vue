<template>
  <div class="icon">
    <div class="hourglass"></div>
  </div>
</template>

<script>
  export default {
    name: 'LoadingIcon'
  }
</script>

<style scoped>
/* Fuente: https://codepen.io/jkantner/pen/wvWXyKG */

.icon {
  transform: rotate(180deg) scale(-0.4);
}

.hourglass, .hourglass:before, .hourglass:after {
  animation-duration: 4s;
  animation-iteration-count: infinite;
}
.hourglass {
  position: relative;
  width: 5em;
  height: 9em;
  z-index: 0;
  animation-name: flip;
  animation-timing-function: ease-in-out;
  background-image: linear-gradient(#255ff4 0.5em,#737a8c55 0.5em 8.5em, #255ff4 8.5em);
  --polygonH: polygon(0% 0%,100% 0%,100% 5.55%,95% 5.55%,95% 28%,60% 46%,60% 54%,95% 72%,95% 94.45%,100% 94.45%,100% 100%,0% 100%,0% 94.45%,5% 94.45%,5% 72%,40% 54%,40% 46%,5% 28%,5% 5.55%,0% 5.55%);
  clip-path: var(--polygonH);
  overflow: hidden;
}

.hourglass:before, .hourglass:after {
  content: "";
  display: block;
  position: absolute;
  animation-timing-function: linear;
}

.hourglass:before {
  top: 0.5em;
  left: 0.5em;
  width: 4em;
  height: 8em;
  background-color: #c7cad1;
  background-size: 100% 3.6em;
  --polygonB1: polygon(0% 0%,100% 0%,100% 24%,50% 47%,50% 47%,50% 47%,50% 47%,50% 47%,50% 47%,50% 47%,50% 47%,0% 24%);
  --polygonB2: polygon(0% 4%,100% 4%,100% 24%,55% 45%,55% 100%,55% 100%,55% 100%,45% 100%,45% 100%,45% 100%,45% 45%,0% 24%);
  --polygonB3: polygon(0% 24%,100% 24%,100% 24%,55% 45%,55% 80%,100% 100%,100% 100%,0% 100%,0% 100%,45% 80%,45% 45%,0% 24%);
  --polygonB4: polygon(45% 45%,55% 45%,55% 45%,55% 45%,55% 58%,100% 76%,100% 100%,0% 100%,0% 76%,45% 58%,45% 45%,45% 45%);
  --polygonB5: polygon(50% 53%,50% 53%,50% 53%,50% 53%,50% 53%,100% 76%,100% 100%,0% 100%,0% 76%,50% 53%,50% 53%,50% 53%);
  clip-path: var(--polygonB1);
  animation-name: fill;
  z-index: 1;
}

.hourglass:after {
  top: 0;
  left: -3em;
  width: 200%;
  height: 100%;
  background:
    linear-gradient(90deg,#0000 0.5em,#0003 0.5em 1.5em,#0000 1.5em 3.5em,#fff3 3.5em 4.5em,#fff0 4.5em 6.5em,#0003 6.5em 7.5em,#0000 7.5em) 0 0 / 100% 0.5em,
    linear-gradient(90deg,#0000 0.75em,#0003 0.75em 1.25em,#0000 1.25em 3.75em,#fff3 3.75em 4.25em,#fff0 4.25em 6.75em,#0003 6.75em 7.25em,#0000 7.25em) 0 0.5em / 100% 8em,
    linear-gradient(90deg,#0000 0.5em,#0003 0.5em 1.5em,#0000 1.5em 3.5em,#fff3 3.5em 4.5em,#fff0 4.5em 6.5em,#0003 6.5em 7.5em,#0000 7.5em) 0 100% / 100% 0.5em;
  background-repeat: repeat-x;
  animation-name: glare;
  z-index: 2;
}

@keyframes fill {
  from {
    clip-path: var(--polygonB1);
  }
  10% {
    clip-path: var(--polygonB2);
  }
  45% {
    clip-path: var(--polygonB3);
  }
  80% {
    clip-path: var(--polygonB4);
  }
  85%, to {
    clip-path: var(--polygonB5);
  }
}

@keyframes glare {
  from, 90% {
    transform: translateX(0);
  }
  to {
    transform: translateX(3em);
  }
}

@keyframes flip {
  from, 90% {
    transform: rotate(0);
  }
  to {
    transform: rotate(180deg);
  }
}
</style>