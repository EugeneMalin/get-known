/**
 * Компонент для отображения слайдера с данными
 */
<template>
  <a-list class="slider" :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }" :dataSource="data">
    <a-list-item class="slider-item" slot="renderItem" slot-scope="item, index">
      <a-card class="slider-content">item.content</a-card>
    </a-list-item>
  </a-list>
</template>

<script>
export default {

}
</script>

<style>

</style> */