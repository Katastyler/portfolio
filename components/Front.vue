<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="page front">
      <div class="center">
        <h1>Front</h1>
        <p class="vertical-p">E</p>
        <p class="vertical-p">N</p>
        <p class="vertical-p">D</p>
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
        rotationY: 90,
        transformOrigin: '50% 50%'
      })

      tl.to(el, 1, {
        autoAlpha: 1,
        rotationY: 0,
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
.vertical-p {
  margin:7px;
}
</style>
