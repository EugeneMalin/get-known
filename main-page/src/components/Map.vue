/**
 * 
 */
<template>
  <div class="map">
    <img class="map-image" src="@/assets/world.png"/>
    <Title class="map-title" :header="title"/>
        <div class="map-picker" @click="_showReport(point)" :style="_handlePosition(point)" v-for="point in points" :key="point.index">
            <img class="map-face" :src="point.photoUrl" v-if="point.photoUrl"/>
            <img class="map-face" src="@/assets/teacher3.png" v-else/>
        </div>
  </div>
</template>

<script>
import Title from './Title'
export default {
    components: {
        Title
    },
    props: {
        title: String,
        points: Array
    },
    methods: {
        _handlePosition(point) {
            return `left: ${point.posX * 25 / 39}%;top: ${point.posY * 20 / 13}%`
        },
        _showReport(point) {
            //Todo надо добавить метод который вернет отзыв пользователя
            console.log(point.index)
            point.report =  'Супер пупер мега вау занимаюсь 5 лет и буду дальше'
            point.visible = !point.visible
        }
    }
}
</script>

<style lang="less">
    @iconSize: 66px;
    @iconMargin: 33px;
    @iconSizeHovered: 70px;
    @iconMarginHovered: 35px;

    .map {
        position: relative;
        display: flex;
        width: 100%;
        height: 100%;
        &-image {
            width: 100%;
            height: 100%;
        }
        &-title {
            position: absolute;
            top: 50%;
            left: 50%;
            margin-right: -50%;
            transform: translate(-50%, -50%);
            z-index: 2;
        }
        &-picker {
            cursor: pointer;
            position: absolute;
            width: @iconSize;
            height: @iconSize;
            border-radius: 50%;
            overflow: hidden;
            background: #C4C4C4;
            margin-left: -@iconMargin;
            margin-top: -@iconMargin;
        }
        &-picker:hover {
            position: absolute;
            border-radius: 50%;
            margin-left: -@iconMarginHovered;
            margin-top: -@iconMarginHovered;
            width: @iconSizeHovered;
            height: @iconSizeHovered;;
            z-index: 3;
            background: linear-gradient(99.63deg, #5068EF 0%, #7A59F6 97.61%);
        }
        &-face {
            display: block;
            margin-left: auto;
            margin-right: auto;
            max-width: 120%;
            max-height: 120%;
        }
    }
</style>