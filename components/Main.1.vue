<template>
  <div class="container">
    <div class="circle">
      <div class="title">
        <h1>
          Hello, my name is
          <span class="name">Miguel Catalina</span>
        </h1>
        <h1>I'm a Full Stack web developer</h1>
        <a-button ghost class="btn-skills">
          <a-icon type="message"/>Contact me
        </a-button>
      </div>
      <a class="up-icon">
        <a-icon type="up"/>
        <div class="extremes">Others</div>
      </a>
      <a class="right-icon">
        <div class="extremes">Backend</div>
        <a-icon type="right"/>
      </a>
      <a class="down-icon">
        <div class="extremes">Labs</div>
        <a-icon type="down"/>
      </a>
      <a class="left-icon" @click="setView()">
        <a-icon type="left"/>
        <div class="extremes">Frontend</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  /* eslint-disable */
  methods: {
    setView: () => {
      console.log('hey')
    }
  }
}
</script>


<style>
.name {
  color: firebrick;
  text-decoration: underline;
}
.title {
  width: 80%;
  text-align: center;
}

.title h1 {
  color: rgb(65, 48, 48);
  font-size: 40px;
}

.circle {
  position: relative;
  width: 80vh;
  height: 80vh;
  border: 2px solid rgb(65, 48, 48);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.circle .extremes {
  font-size: 30px;
  position: absolute;
}

.up-icon {
  position: absolute;
  right: calc(50% - 13px);
  top: 0;
  color: rgb(65, 48, 48);
}

.up-icon div {
  left: -30px;
}

.down-icon {
  position: absolute;
  right: calc(50% - 13px);
  bottom: 0;
  color: rgb(65, 48, 48);
}

.down-icon div {
  left: -15px;
  bottom: 20px;
}

.left-icon {
  position: absolute;
  top: 50%;
  left: 0;
  color: rgb(65, 48, 48);
}

.left-icon div {
  left: 25px;
  top: -15px;
}

.right-icon {
  position: absolute;
  top: 50%;
  right: 0;
  color: rgb(65, 48, 48);
}

.right-icon div {
  left: -110px;
  top: -15px;
}

.btn-skills {
  height: 100%;
  font-size: 30px;
  color: rgb(65, 48, 48);
}
</style>
