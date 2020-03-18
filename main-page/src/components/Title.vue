/**
 * Компонент для отображение заголовка с подсказкой
 */
<template>
  <div class="title">
      <span class="title-header"> {{ header }} </span>
      <span class="title-description">{{ description }}</span>
  </div>
</template>

<script>
export default {
    props: {
        header: String,
        description: String
    }
}
</script>

<style>
    .title {
        display: flex;
        flex-direction: column;
    }
    .title-header {
        font-family: Roboto;
        font-style: normal;
        font-weight: 900;
        font-size: 58px;
        line-height: 68px;
        text-align: center;
        color: #000000;
    }
    .title-description {
        font-family: Roboto;
        font-style: normal;
        font-weight: 300;
        font-size: 18px;
        line-height: 36px;
        text-align: center;
        color: #545464;
    }
</style>