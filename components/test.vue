<template>
  <a-layout class="container">
    <a-layout-header class="header">
      <a-row>
        <a-col :xl="22" :xs="17" :md="21">
          <h1>Miguel Catalina</h1>
        </a-col>
        <a-col :xl="2" :xs="7" :md="3">
          <a-dropdown>
            <a class="ant-dropdown-link" href="#">Work
              <a-icon type="down"/>
            </a>
            <a-menu slot="overlay">
              <a-menu-item key="1">
                <a-icon type="eye"/>1st menu item
              </a-menu-item>
              <a-menu-item key="2">
                <a-icon type="eye"/>2nd menu item
              </a-menu-item>
              <a-menu-item key="3">
                <a-icon type="eye"/>3rd item
              </a-menu-item>
            </a-menu>
          </a-dropdown>
        </a-col>
      </a-row>
    </a-layout-header>
    <a-layout-content>
      <div class="content-container">
        <a-row :gutter="40">
          <a-col v-for="card in cards" :key="card.title" class="project-card" :md="8" :sm="24">
            <a-card :title="card.title" hoverable>
              <a :href="card.href" slot="extra">
                <a-icon type="rocket"/>
              </a>
              <p>{{ card.info }}</p>
            </a-card>
          </a-col>
        </a-row>
      </div>
    </a-layout-content>
    <a-layout-footer class="footer">Ant Design ©2018 Created by Ant UED</a-layout-footer>
  </a-layout>
</template>

<script>
export default {
  name: '',
  transition: 'bounce',
  data: function() {
    return {
      cards: [
        {
          title: 'Vue.js / Nuxt.js',
          href: 'vue-nuxt',
          info: 'hbasdhklibasldfbfkl'
        },
        {
          title: 'AngularJS / React',
          href: '/',
          info: 'angular-react'
        },
        {
          title: 'Node.js',
          href: 'a',
          info: 'a'
        },
        {
          title: 'Electron',
          href: 'a',
          info: 'a'
        },
        {
          title: 'PostgreSQL',
          href: 'a',
          info: 'a'
        },
        {
          title: 'Python',
          href: 'a',
          info: 'a'
        },
        {
          title: 'Linux Scripting',
          href: 'a',
          info: 'a'
        },
        {
          title: 'Salesforce Lightning',
          href: 'a',
          info: 'a'
        }
      ]
    }
  },
  methods() {}
}
</script>


<style>
.content-container {
  padding: 30px;
}

.project-card {
  padding-bottom: 16px;
}

.project-card div {
  max-width: 22rem;
  margin: auto;
}
</style>
