<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="page about">
        <a-row class="">
          <a-col :span="24" class="photo-container">
            <img class="photo" src="~/static/retrato.jpg"/>
          </a-col>
        </a-row>
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
        scale: 2,
        transformOrigin: '50% 50%'
      })

      tl.to(el, 1, {
        autoAlpha: 1,
        scale: 1,
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
.photo {
  height: 400px;
}

.photo-container {
  padding: 5%;
  text-align: center;
}
</style>
