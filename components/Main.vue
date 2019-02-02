<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="main">
      <div class="title">
        <h1 class="agent-3">
          Hello, my name is
          <a id="my-name">Miguel Catalina</a>
        </h1>
        <h1 class="agent-3">I'm a Full Stack web developer</h1>
      </div>
      <div id="canvas"/>
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
    particlesJS('canvas', {
      particles: {
        number: { value: 100, density: { enable: true, value_area: 800 } },
        color: { value: '#ffffff' },
        shape: {
          type: 'circle',
          stroke: { width: 0, color: '#000000' },
          polygon: { nb_sides: 5 },
          image: { src: 'img/github.svg', width: 100, height: 100 }
        },
        opacity: {
          value: 1,
          random: true,
          anim: { enable: true, speed: 1, opacity_min: 0, sync: false }
        },
        size: {
          value: 3,
          random: true,
          anim: { enable: false, speed: 4, size_min: 0.3, sync: false }
        },
        line_linked: {
          enable: false,
          distance: 150,
          color: '#ffffff',
          opacity: 0.4,
          width: 1
        },
        move: {
          enable: true,
          speed: 1,
          direction: 'none',
          random: true,
          straight: false,
          out_mode: 'out',
          bounce: false,
          attract: { enable: false, rotateX: 600, rotateY: 600 }
        }
      },
      interactivity: {
        detect_on: 'canvas',
        events: {
          onhover: { enable: true, mode: 'bubble' },
          // onclick: { enable: true, mode: 'grab' },
          resize: true
        },
        modes: {
          grab: { distance: 400, line_linked: { opacity: 1 } },
          bubble: { distance: 0, size: 0, duration: 2, opacity: 0, speed: 3 },
          repulse: { distance: 400, duration: 0.4 },
          push: { particles_nb: 4 },
          remove: { particles_nb: 2 }
        }
      },
      retina_detect: true
    })
  }
}
</script>


<style scoped>
.title {
  position: absolute;
  width: 100%;
  text-align: center;
  height: 100%;
  top: 28%;
  z-index: 0;  
}

#canvas {
  height: 100%;
}

#my-name {
  color: firebrick;
  position: relative;
  color: firebrick;
  text-decoration: none;
}

#my-name:before {
  content: '';
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: -5px;
  left: 0;
  background-color: firebrick;
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
</style>
