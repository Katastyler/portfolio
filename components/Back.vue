<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="page back">
      <div class="center">
        <gallery :projects="projects"/>
      </div>
    </div>
  </transition>
</template>

<script>
import Gallery from '@/components/Gallery.vue'

export default {
  /* eslint-disable */
  data() {
    return {
      projects: [
        {
          title: 'Geolocation',
          subtitle: 'Vue.js / Leaflet / Node.js',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AAAA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },
        {
          title: 'Festivals Web search',
          subtitle: 'Vue.js / Nuxt.js / Node.js',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },
        {
          title: 'Desktop App Salesforce ETL',
          subtitle: 'Electron / Node.js / Vue.js',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },
        {
          title: 'Tagliatella Mobile App',
          subtitle: 'React / Angular / Ionic',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },
        {
          title: 'Marketing Landing Pages',
          subtitle: 'Pure HTLM / Pure JS',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },
        {
          title: 'Smart2 Sensor Technology Website',
          subtitle: 'Wordpress / PHP',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },
        {
          title: 'Smart3 Sensor Technology Website',
          subtitle: 'Wordpress / PHP',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },
        {
          title: 'Smart Sensor Technology Website',
          subtitle: 'Wordpress / PHP',
          modal: {
            visible: false,
            img: {
              'background-image': 'url(' + require('~/static/king.png') + ')'
            },
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        }
      ]
    }
  },
  components: {
    Gallery
  },
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
    },
    showModal(index) {
      this.projects[index].modal.visible = true
    },
    handleOk(e) {
      console.log(e)
      this.visible = false
    }
  }
}
</script>


<style>
.back {
  height: calc(100% - 100px);
}
</style>
