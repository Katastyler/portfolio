<template>
  <div id="app">
    <component :is="state.view"/>
    <div>
      <ul class="controls">
        <li
          v-for="(animation) in state.animations"
          @click.prevent="setView(animation)"
          v-bind:class="{ 'active': animation === state.view }"
          :key="animation"
        >{{ animation }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Main from '@/components/Main.vue'
import Front from '@/components/Front.vue'
import Back from '@/components/Back.vue'
import Labs from '@/components/Labs.vue'
import About from '@/components/About.vue'

export default {
  /* eslint-disable */
  name: 'Portfolio',
  components: {
    Main,
    Front,
    Back,
    Labs,
    About
  },
  data() {
    return {
      state: {
        animations: ['Main', 'Front', 'Back', 'Labs', 'About'],
        view: 'Main'
      }
    }
  },
  methods: {
    setView(animation) {
      this.state.view = animation
    }
  }
}
</script>