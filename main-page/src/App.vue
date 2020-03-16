<template>
  <div class="app">
    <Cover />
    <div class="cals">aaaaaaa</div>
  </div>
</template>

<script>

import Cover from './components/Cover'

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
    Cover
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
