<template>
  <div class="notifications">
    <mark v-if="value < 100" :class="animation" :style="getStyle">{{value}}</mark>
    <mark v-else>99+</mark>
  </div>
</template>

<script>
  export default {
    props: {
      value: Number,
      animation: String,
      color: {
        type: String,
        default: '#FFFFFF'
      },
      background: {
        type: String,
        default: '#FF6B6B'
      }
    },
    methods: {
      getStyle () {
        return {
          color: this.color,
          background: this.background
        }
      }
    }
  }
</script>

<style scoped>
  .notifications {
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    position: absolute;
  }
  mark {
    border-radius: 20px;   
    border: 2px solid #FFF;
    width: 20px;
    height: 20px;
    text-align: center;
    position: absolute;
    top: -5px;
    left: -10px;
    font-size: 10px;
    line-height: 20px;
    font-family: 'Roboto', sans-serif;
    font-weight: 400;
    font-weight: 700;
  }
  mark.big {
    width: 30px;
    height: 30px;
    border-radius: 30px;
    line-height: 30px;  
    font-size: 16px;  
    top: -10px;
    left: -15px;
  }
  .notifications > mark {
    -webkit-animation-name: bounceIn;
            animation-name: bounceIn;
    -webkit-transform-origin: center bottom;
            transform-origin: center bottom;
    -webkit-animation-duration: 1s;
            animation-duration: 1s;
    -webkit-animation-fill-mode: both;
            animation-fill-mode: both;   
    -webkit-animation-iteration-count: 1;
            animation-iteration-count: 1;  
  }
  .notifications:hover > mark {
    -webkit-animation-name: bounce;
            animation-name: bounce;
  }
  .notifications:hover > mark.rubberBand {
    -webkit-animation-name: rubberBand;
            animation-name: rubberBand;
  }

  .notifications:hover > mark.swing {
    -webkit-transform-origin: top center;
            transform-origin: top center;
    -webkit-animation-name: swing;
            animation-name: swing;
  }
  .notifications:hover > mark.tada {
    -webkit-animation-name: tada;
            animation-name: tada;
  }
  .notifications:hover > mark.wobble {
    -webkit-animation-name: wobble;
            animation-name: wobble;
  }

  /* animation keyframes */
  @-webkit-keyframes bounce {
    0%, 20%, 53%, 80%, 100% {
      transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
      -webkit-transform: translate3d(0,0,0);
              transform: translate3d(0,0,0);
    }

    40%, 43% {
      transition-timing-function: cubic-bezier(0.755, 0.050, 0.855, 0.060);
      -webkit-transform: translate3d(0, -30px, 0);
              transform: translate3d(0, -30px, 0);
    }

    70% {
      transition-timing-function: cubic-bezier(0.755, 0.050, 0.855, 0.060);
      -webkit-transform: translate3d(0, -15px, 0);
              transform: translate3d(0, -15px, 0);
    }

    90% {
      -webkit-transform: translate3d(0,-4px,0);
              transform: translate3d(0,-4px,0);
    }
  }

  @keyframes bounce {
    0%, 20%, 53%, 80%, 100% {
      transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
      -webkit-transform: translate3d(0,0,0);
              transform: translate3d(0,0,0);
    }

    40%, 43% {
      transition-timing-function: cubic-bezier(0.755, 0.050, 0.855, 0.060);
      -webkit-transform: translate3d(0, -30px, 0);
              transform: translate3d(0, -30px, 0);
    }

    70% {
      transition-timing-function: cubic-bezier(0.755, 0.050, 0.855, 0.060);
      -webkit-transform: translate3d(0, -15px, 0);
              transform: translate3d(0, -15px, 0);
    }

    90% {
      -webkit-transform: translate3d(0,-4px,0);
              transform: translate3d(0,-4px,0);
    }
  }

  @-webkit-keyframes bounceIn {
    0%, 20%, 40%, 60%, 80%, 100% {
      transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
    }

    0% {
      opacity: 0;
      -webkit-transform: scale3d(.3, .3, .3);
              transform: scale3d(.3, .3, .3);
    }

    20% {
      -webkit-transform: scale3d(1.1, 1.1, 1.1);
              transform: scale3d(1.1, 1.1, 1.1);
    }

    40% {
      -webkit-transform: scale3d(.9, .9, .9);
              transform: scale3d(.9, .9, .9);
    }

    60% {
      opacity: 1;
      -webkit-transform: scale3d(1.03, 1.03, 1.03);
              transform: scale3d(1.03, 1.03, 1.03);
    }

    80% {
      -webkit-transform: scale3d(.97, .97, .97);
              transform: scale3d(.97, .97, .97);
    }

    100% {
      opacity: 1;
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }
  }

  @keyframes bounceIn {
    0%, 20%, 40%, 60%, 80%, 100% {
      transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
    }

    0% {
      opacity: 1;
      -webkit-transform: scale3d(.3, .3, .3);
              transform: scale3d(.3, .3, .3);
    }

    20% {
      -webkit-transform: scale3d(1.1, 1.1, 1.1);
              transform: scale3d(1.1, 1.1, 1.1);
    }

    40% {
      -webkit-transform: scale3d(.9, .9, .9);
              transform: scale3d(.9, .9, .9);
    }

    60% {
      opacity: 1;
      -webkit-transform: scale3d(1.03, 1.03, 1.03);
              transform: scale3d(1.03, 1.03, 1.03);
    }

    80% {
      -webkit-transform: scale3d(.97, .97, .97);
              transform: scale3d(.97, .97, .97);
    }

    100% {
      opacity: 1;
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }
  }
  @-webkit-keyframes rubberBand {
    0% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }

    30% {
      -webkit-transform: scale3d(1.25, 0.75, 1);
              transform: scale3d(1.25, 0.75, 1);
    }

    40% {
      -webkit-transform: scale3d(0.75, 1.25, 1);
              transform: scale3d(0.75, 1.25, 1);
    }

    50% {
      -webkit-transform: scale3d(1.15, 0.85, 1);
              transform: scale3d(1.15, 0.85, 1);
    }

    65% {
      -webkit-transform: scale3d(.95, 1.05, 1);
              transform: scale3d(.95, 1.05, 1);
    }

    75% {
      -webkit-transform: scale3d(1.05, .95, 1);
              transform: scale3d(1.05, .95, 1);
    }

    100% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }
  }

  @keyframes rubberBand {
    0% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }

    30% {
      -webkit-transform: scale3d(1.25, 0.75, 1);
              transform: scale3d(1.25, 0.75, 1);
    }

    40% {
      -webkit-transform: scale3d(0.75, 1.25, 1);
              transform: scale3d(0.75, 1.25, 1);
    }

    50% {
      -webkit-transform: scale3d(1.15, 0.85, 1);
              transform: scale3d(1.15, 0.85, 1);
    }

    65% {
      -webkit-transform: scale3d(.95, 1.05, 1);
              transform: scale3d(.95, 1.05, 1);
    }

    75% {
      -webkit-transform: scale3d(1.05, .95, 1);
              transform: scale3d(1.05, .95, 1);
    }

    100% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }
  }
  @-webkit-keyframes swing {
    20% {
      -webkit-transform: rotate3d(0, 0, 1, 15deg);
              transform: rotate3d(0, 0, 1, 15deg);
    }

    40% {
      -webkit-transform: rotate3d(0, 0, 1, -10deg);
              transform: rotate3d(0, 0, 1, -10deg);
    }

    60% {
      -webkit-transform: rotate3d(0, 0, 1, 5deg);
              transform: rotate3d(0, 0, 1, 5deg);
    }

    80% {
      -webkit-transform: rotate3d(0, 0, 1, -5deg);
              transform: rotate3d(0, 0, 1, -5deg);
    }

    100% {
      -webkit-transform: rotate3d(0, 0, 1, 0deg);
              transform: rotate3d(0, 0, 1, 0deg);
    }
  }

  @keyframes swing {
    20% {
      -webkit-transform: rotate3d(0, 0, 1, 15deg);
              transform: rotate3d(0, 0, 1, 15deg);
    }

    40% {
      -webkit-transform: rotate3d(0, 0, 1, -10deg);
              transform: rotate3d(0, 0, 1, -10deg);
    }

    60% {
      -webkit-transform: rotate3d(0, 0, 1, 5deg);
              transform: rotate3d(0, 0, 1, 5deg);
    }

    80% {
      -webkit-transform: rotate3d(0, 0, 1, -5deg);
              transform: rotate3d(0, 0, 1, -5deg);
    }

    100% {
      -webkit-transform: rotate3d(0, 0, 1, 0deg);
              transform: rotate3d(0, 0, 1, 0deg);
    }
  }

  @-webkit-keyframes tada {
    0% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }

    10%, 20% {
      -webkit-transform: scale3d(.9, .9, .9) rotate3d(0, 0, 1, -3deg);
              transform: scale3d(.9, .9, .9) rotate3d(0, 0, 1, -3deg);
    }

    30%, 50%, 70%, 90% {
      -webkit-transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, 3deg);
              transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, 3deg);
    }

    40%, 60%, 80% {
      -webkit-transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, -3deg);
              transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, -3deg);
    }

    100% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }
  }

  @keyframes tada {
    0% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }

    10%, 20% {
      -webkit-transform: scale3d(.9, .9, .9) rotate3d(0, 0, 1, -3deg);
              transform: scale3d(.9, .9, .9) rotate3d(0, 0, 1, -3deg);
    }

    30%, 50%, 70%, 90% {
      -webkit-transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, 3deg);
              transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, 3deg);
    }

    40%, 60%, 80% {
      -webkit-transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, -3deg);
              transform: scale3d(1.1, 1.1, 1.1) rotate3d(0, 0, 1, -3deg);
    }

    100% {
      -webkit-transform: scale3d(1, 1, 1);
              transform: scale3d(1, 1, 1);
    }
  }

  @-webkit-keyframes wobble {
    0% {
      -webkit-transform: none;
              transform: none;
    }

    15% {
      -webkit-transform: translate3d(-25%, 0, 0) rotate3d(0, 0, 1, -5deg);
              transform: translate3d(-25%, 0, 0) rotate3d(0, 0, 1, -5deg);
    }

    30% {
      -webkit-transform: translate3d(20%, 0, 0) rotate3d(0, 0, 1, 3deg);
              transform: translate3d(20%, 0, 0) rotate3d(0, 0, 1, 3deg);
    }

    45% {
      -webkit-transform: translate3d(-15%, 0, 0) rotate3d(0, 0, 1, -3deg);
              transform: translate3d(-15%, 0, 0) rotate3d(0, 0, 1, -3deg);
    }

    60% {
      -webkit-transform: translate3d(10%, 0, 0) rotate3d(0, 0, 1, 2deg);
              transform: translate3d(10%, 0, 0) rotate3d(0, 0, 1, 2deg);
    }

    75% {
      -webkit-transform: translate3d(-5%, 0, 0) rotate3d(0, 0, 1, -1deg);
              transform: translate3d(-5%, 0, 0) rotate3d(0, 0, 1, -1deg);
    }

    100% {
      -webkit-transform: none;
              transform: none;
    }
  }

  @keyframes wobble {
    0% {
      -webkit-transform: none;
              transform: none;
    }

    15% {
      -webkit-transform: translate3d(-25%, 0, 0) rotate3d(0, 0, 1, -5deg);
              transform: translate3d(-25%, 0, 0) rotate3d(0, 0, 1, -5deg);
    }

    30% {
      -webkit-transform: translate3d(20%, 0, 0) rotate3d(0, 0, 1, 3deg);
              transform: translate3d(20%, 0, 0) rotate3d(0, 0, 1, 3deg);
    }

    45% {
      -webkit-transform: translate3d(-15%, 0, 0) rotate3d(0, 0, 1, -3deg);
              transform: translate3d(-15%, 0, 0) rotate3d(0, 0, 1, -3deg);
    }

    60% {
      -webkit-transform: translate3d(10%, 0, 0) rotate3d(0, 0, 1, 2deg);
              transform: translate3d(10%, 0, 0) rotate3d(0, 0, 1, 2deg);
    }

    75% {
      -webkit-transform: translate3d(-5%, 0, 0) rotate3d(0, 0, 1, -1deg);
              transform: translate3d(-5%, 0, 0) rotate3d(0, 0, 1, -1deg);
    }

    100% {
      -webkit-transform: none;
              transform: none;
    }
  }
</style>
