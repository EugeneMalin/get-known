<template>
  <div class="app">
    <Cover class="app-cover"/>
    <Invitation class="app-invitation"/>
  </div>
</template>

<script>

import Cover from './components/Cover'
import Invitation from './components/Invitation'
import Antd from 'ant-design-vue';
import Vue from 'vue';
import 'ant-design-vue/dist/antd.css'

Vue.use(Antd);

const navigationItems = [
  {
    id: 'about',
    checked: false,
    marker: null,
    title: 'О школе'
  },
  {
    id: 'courses',
    checked: false,
    marker: '1 бесплатный',
    title: 'Курсы'
  },
  {
    id: 'teachers',
    checked: false,
    marker: null,
    title: 'Преподаватели'
  },
  {
    id: 'forYou',
    checked: false,
    marker: null,
    title: 'Для вас'
  }
]

export default {
  name: 'App',
  components: {
    Cover,
    Invitation
  },
  data() {
    return {
      navigationItems
    }
  }
}
</script>

<style>
.app {
    height: 4000px;
}
html, body {
    height: 100%;
    margin: 0;
    padding: 0;
    overflow-x: hidden;
}
main {
    min-height: 100%;
}
</style>
