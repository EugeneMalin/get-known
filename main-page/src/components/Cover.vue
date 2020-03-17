/**
 * Компонент для отображения титульного элемента сайта
 * Отображает приветственное изображение логотип и панель навигации с кнопками
 */

<template>
  <div class="cover">
    <img class="cover-image" src="@/assets/cover.svg"/>
    <div class="cover-logotext">GetKnow</div>
    <div class="cover-description">
        Онлайн-школа с живым обучением по видеосвязи, проверкой Д/З и экзаменами
    </div>
  </div>
</template>

<script>
export default {
    name: 'Cover'
}
</script>

<style>
.cover {
    width: 100%;
    position: relative;
}
.cover .cover-logotext {
    padding-top: calc(100vh * 0.377);
}
.cover-image {
    width: 100vw;
    height: 100vh;
    object-fit: cover;
}
.cover-logotext {
    font-family: Roboto;
    font-style: normal;
    font-weight: 900;
    font-size: 124px;
    line-height: 145px;
    text-align: center;
    color: #324BC0;
}
.cover-description {
    font-family: Roboto;
    font-style: normal;
    font-weight: 300;
    font-size: 24px;
    line-height: 170%;
    /* or 41px */

    text-align: center;
    color: #545464;
}

</style>