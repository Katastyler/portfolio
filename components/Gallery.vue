<template>
  <a-row type="flex" justify="center">
    <a-col
      class="project-container"
      v-for="(project, index) in projects"
      :key="project.title"
      :style="project.modal.img"
    >
      <div class="text">
        <div class="title">{{ project.title }}</div>
        <span class="sub-title">{{ project.subtitle }}</span>
      </div>
      <a-button class="btn-project" ghost type="primary" @click="showModal(index)">Learn More</a-button>
      <a-modal 
        :footer="null" 
        :title="project.modal.title" 
        centered 
        v-model="project.modal.visible" 
        @ok="handleOk">
        <div>
          {{ project.modal.description }}
        </div>
      </a-modal>
    </a-col>
  </a-row>
</template>

<script>
export default {
  /* eslint-disable */
  props: {
    projects: {
      type: Array,
      default: function() {
        return []
      }
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
.project-container {
  transition: .5s;
  display: inline-block;
  width: 390px;
  height: 300px;
  background-color: #505050;
}

.project-container:hover {
  background-image: none !important;
}

.text {
  font-size: 1.8rem;
  top: 0; 
  left: 0;
  position: relative;
  width: 100%;
  top: 0%;
  transition: 0.8s;
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

.project-container:hover .btn-project {
  top: 20%;
  z-index: 1;
}

.btn-project {
  top: 30%;
  left: 0;
  position: relative;
  width: 40%;
  transition: 0.8s;
  z-index: -1;
}
</style>
