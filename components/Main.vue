<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="main">
      <div class="title agent-1">
        <h1>
          Hello, my name is
          <a id="my-name">Miguel Catalina</a>
        </h1>
        <h1>I'm a Full Stack web developer</h1>
        <div class="subtitle-container">
          <p class="agent-3">
            <img class="icon-main" src="~/static/project.svg">Expertise in all project cycle.
          </p>
          <p class="agent-3">
            <img class="icon-main" src="~/static/creative.svg">Out of the box / lateral thinking.
          </p>
          <p class="agent-3">
            <img class="icon-main" src="~/static/browser.svg">Passion at work.
          </p>
          <p class="agent-3">
            <img class="icon-main" src="~/static/science.svg">'One man army' of web development.
          </p>
        </div>
      </div>
      <div id="canvas"/>
      <div class="see-more">
        <p class="arrow-text">Want to see more?</p>
        <img class="arrow" src="~/static/down-arrow.svg">
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  /* eslint-disable */
  methods: {
    enter(el, done) {
      TweenMax.fromTo(
        el,
        1,
        {
          autoAlpha: 0,
          scale: 1.5
        },
        {
          autoAlpha: 1,
          scale: 1,
          transformOrigin: '50% 50%',
          ease: Power4.easeOut,
          onComplete: done
        }
      )
    },
    leave(el, done) {
      TweenMax.fromTo(
        el,
        1,
        {
          autoAlpha: 1,
          scale: 1
        },
        {
          autoAlpha: 0,
          scale: 0.8,
          ease: Power4.easeOut,
          onComplete: done
        }
      )
    }
  },
  mounted() {
    const config = require('~/assets/particles.json')
    particlesJS('canvas', config)
  }
}
</script>


<style scoped>
.title {
  position: absolute;
  width: 100%;
  text-align: center;
  height: 100%;
  top: 10vh;
  z-index: 0;
  padding: 0.4rem;
}

#canvas {
  height: 100%;
}

#my-name {
  color: rgb(216, 88, 42);
  position: relative;
  text-decoration: none;
}

#my-name:before {
  content: '';
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: -5px;
  left: 0;
  background-color: rgb(216, 88, 42);
  visibility: hidden;
  -webkit-transform: scaleX(0);
  transform: scaleX(0);
  -webkit-transition: all 0.3s ease-in-out 0s;
  transition: all 0.3s ease-in-out 0s;
}

#my-name:hover:before {
  visibility: visible;
  -webkit-transform: scaleX(1);
  transform: scaleX(1);
}

.main {
  height: 100%;
}

.subtitle-container {
  padding: .6rem;
  display: inline-block;
}

.subtitle-container p {
  text-align: left;
}

.icon-main {
  width: 2rem;
  margin-bottom: -0.2rem;
  padding-right: 0.4rem;
}

.arrow-text {
  padding-top: 2.5rem;
  text-align: center !important;
  margin: 0.7rem;
  background: linear-gradient(yellow, firebrick);
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.arrow {
  width: 3rem;
  animation: mover 0.7s infinite alternate;
}

@keyframes mover {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-2px);
  }
}

.see-more {
  position: absolute;
  width: 100%;
  text-align: center;
  bottom: 90px;
}
</style>
