/**
 * 
 */
<template>
  <div class="map">
    <img class="map-image" src="@/assets/world.png"/>
    <div class="map-title"></div>
  </div>
</template>

<script>
export default {
    props: {
        title: String,
        points: Array
    }
}
</script>

<style lang="less">
    .map {
        position: relative;
        display: flex;
        width: 100%;
        height: 100%;
        &-image {
            width: 100%;
            height: 100%;
        }
    }
</style>