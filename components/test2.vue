<template>
  <div class="container">
    <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false">
      <Main/>
    </transition>
  </div>
</template>

<script>
import Main from '@/components/Main.vue'

export default {
  /* eslint-disable */
  components: {
    Main
  },
  name: 'Portfolio',
  methods: {
    enter: (el, done) => {
      const tl = new TimelineMax({
        onComplete: done
      })

      tl.set(el, {
        x: window.innerWidth * 1.5,
        scale: 0.8,
        transformOrigin: '50% 50%'
      })

      tl.to(el, 0.5, {
        x: 0,
        ease: Power4.easeOut
      })

      tl.to(el, 1, {
        scale: 1,
        ease: Power4.easeOut
      })
    },
    leave: (el, done) => {
      TweenMax.fromTo(
        el,
        1,
        {
          autoAlpha: 1
        },
        {
          autoAlpha: 0,
          ease: Power4.easeOut,
          onComplete: done
        }
      )
    }
  }
}
</script>

<style scoped>
</style>
