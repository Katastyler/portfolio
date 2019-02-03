<template>
  <transition v-on:enter="enter" v-on:leave="leave" v-bind:css="false" appear>
    <div class="page front">
      <div class="center">
        <h1>Front</h1>
        <div>
          <a-row type="flex" justify="center">
            <a-col class="project-container" v-for="project in projects" :key="project.title">
              <div class="text">
                <div class="title">{{ project.title }}</div>
                <span class="sub-title">{{ project.subtitle }}</span>
              </div>
              <a-button type="primary" @click="showModal">Open Modal</a-button>
            </a-col>
          </a-row>
        </div>

        <a-modal title="Basic Modal" centered v-model="visible" @ok="handleOk">
          <p>Some contents...</p>
          <p>Some contents...</p>
          <p>Some contents...</p>
        </a-modal>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  /* eslint-disable */
  data() {
    return {
      projects: [
        {
          title: 'Geolocation',
          subtitle: 'Vue.js / Leaflet / Node.js',
          moda: {
            img: '',
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },{
          title: 'Festivals Web search',
          subtitle: 'Vue.js / Nuxt.js / Node.js',
          moda: {
            img: '',
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },{
          title: 'Desktop App Salesforce ETL',
          subtitle: 'Electron / Node.js / Vue.js',
          moda: {
            img: '',
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },{
          title: 'Tagliatella Mobile App',
          subtitle: 'React / Angular / Ionic',
          moda: {
            img: '',
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },{
          title: 'Marketing Landing Pages',
          subtitle: 'Pure HTLM / Pure JS',
          moda: {
            img: '',
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        },{
          title: 'Smart Sensor Technology Website',
          subtitle: 'Wordpress / PHP',
          moda: {
            img: '',
            title: 'AA',
            subtitle: 'BB',
            description: 'CCC'
          }
        }
      ]
    }
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
    showModal() {
      this.visible = true
    },
    handleOk(e) {
      console.log(e)
      this.visible = false
    }
  },
  mounted() {
    console.log(this.projects);
    
  }
}
</script>


<style>
.vertical-p {
  margin: 7px;
}

.project-container {
  background-color: aquamarine;
  transition: 1.2s;
  display: inline-block;
  width: 390px;
  height: 300px;
}

.project-container:hover {
  background-color: black;
  cursor: pointer;
}

.text {
  top: 0;
  left: 0;
  position: relative;
  width: 100%;
  top: 0%;
  transition: .8s;
  z-index: -1;
}

.title {
  font-size: 22px;
}

.sub-title {
  font-size: 18px;
}

.project-container:hover .text {
  top: 10%;
  z-index: 1;
}
</style>
