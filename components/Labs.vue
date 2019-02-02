<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="page labs">
      <div class="center">
        <h1>Labs</h1>
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
        autoAlpha: 0,
        rotationX: 90,
        transformOrigin: '50% 50%'
      })

      tl.to(el, 1, {
        autoAlpha: 1,
        rotationX: 0,
        ease: Power4.easeOut
      })
    },
    leave(el, done) {
      TweenMax.to(el, 1, {
        scale: 0,
        ease: Power4.easeOut,
        onComplete: done
      })
    }
  }
}
</script>


<style>
</style>
