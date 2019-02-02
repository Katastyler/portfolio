<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="page back">
      <div class="center">
        <h1>Back</h1>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  /* eslint-disable */
  methods: {
    enter(el, done) {
      const tl = new TimelineMax({
        onComplete: done
      })

      tl.set(el, {
        y: window.innerWidth * 1.5,
        scale: 0.8,
        transformOrigin: '50% 50%'
      })

      tl.to(el, 0.5, {
        y: 0,
        ease: Power4.easeOut
      })

      tl.to(el, 1, {
        scale: 1,
        ease: Power4.easeOut
      })
    },
    leave(el, done) {
      TweenMax.to(el, 1, {
        y: window.innerHeight * -1.5,
        ease: Power4.easeOut,
        onComplete: done
      })
    }
  }
}
</script>


<style>
</style>
