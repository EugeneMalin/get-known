<template>
  <div class="app">
    <Cover class="app-cover"/>
    <Invitation class="app-invitation" title="Хотите получить бесплатный живой урок?" :isMain="false"/>
    <div class="app-fade">
      <div class="app-advantage">
        <Title header="Удобная платформа для образования" description="Для простоты изучения мы разработали для Вас личный кабинет ученика!" />
      </div>
      <div class="app-courses">
        <Title header="Большой выбор курсов с живыми преподавателями"/>
      </div>
    </div>
    <div class="app-fade">
      <div class="app-teachers">
        <Title class="app-title" header="Познакомьтесь с теми, кто будет ваc учить"/>
      </div>
      <div class="app-classes">
        <Title class="app-title" header="Вот так проходят занятия в GetKnow" description="There are no limits to how — and with whom — you can share. Present to a client or at a conference. Keep presentations private for your team, or publish them for the whole world to see." />
        <!--<img class="app-img app-img__macbook" src="@/assets/macbook.png" alt="">-->
        <img class="app-img app-img__plane" src="@/assets/plane.svg" alt="">
        <div class="app-block app-block__macbook">
          <img class="app-img app-img__frame" src="@/assets/frame.png" alt="">
        </div>
      </div>
      <Map class="app-feedback" title="Отзывы наших учеников" :points="feedbackPoints"/>
    </div>    
    <Invitation class="app-getinvitation" title="Попробуете бесплатное занятие сегодня?" :isMain="true"/>
    <div class="app-footer">
      <div class="app-column">
        <img class="app-logo" src="@/assets/logo.svg" alt="">
        <div class="app-item">© Copyright 2020 GetKnow School</div>
        <div class="app-item">Все права защищены.</div>
      </div>
      <div class="app-column">
        <div class="app-item app-item__header">О школе</div>
        <div class="app-item">Бесплатное занятие</div>
        <div class="app-item">Преподаватели</div>
        <div class="app-item">Курсы</div>
        <div class="app-item">Программы</div>
        <div class="app-item">Подарки</div>
      </div>
      <div class="app-column">
        <div class="app-item app-item__header">Курсы</div>
        <div class="app-item">Китайский язык</div>
        <div class="app-item">Английский язык</div>
        <div class="app-item">Программирование</div>
        <div class="app-item">Скорочтение</div>
      </div>
      <div class="app-column">
        <div class="app-item app-item__header">Узнать больше</div>
        <div class="app-row">
          <img class="app-icon" src="@/assets/icons/vk.svg" alt="">
          <img class="app-icon" src="@/assets/icons/telegram.svg" alt="">
          <img class="app-icon" src="@/assets/icons/instagram.svg" alt="">
          <img class="app-icon" src="@/assets/icons/youtube.svg" alt="">
          <img class="app-icon" src="@/assets/icons/facebook.svg" alt="">
        </div>
        <div class="app-item">Скачать проверочный тест</div>
        <div class="app-item">Скачать ещё что-нибудь</div>
      </div>
    </div>
  </div>
</template>

<script>

import Cover from './components/Cover'
import Title from './components/Title'
import Invitation from './components/Invitation'
import Map from './components/Map'
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
const footerLinks = [
  { 
    link: null,
    type: 'vk'
  },
  { 
    link: null,
    type: 'telegram'
  },
  { 
    link: null,
    type: 'instagram'
  },
  { 
    link: null,
    type: 'youtube'
  },
  { 
    link: null,
    type: 'facebook'
  }
]

const feedbackPoints = [
  {
    index: 0,
    photoUrl: null,
    posX: 60,
    posY: 10
  },
  {
    index: 1,
    photoUrl: null,
    posX: 50,
    posY: 43
  },
  {
    index: 2,
    photoUrl: null,
    posX: 130,
    posY: 40
  },
  {
    index: 3,
    photoUrl: null,
    posX: 150,
    posY: 10
  }
]

export default {
  name: 'App',
  components: {
    Cover,
    Invitation,
    Title,
    Map
  },
  data() {
    return {
      footerLinks,
      navigationItems,
      feedbackPoints
    }
  }
}
</script>

<style lang="less">
.app {
  .app-invitation {
    height: 310px;
  }
  .app-advantage {
    margin-top: 110px;
  }
  .app-getinvitation {
    height: 486px;
  }
  .app-teachers {
    display: flex;
    justify-content: center;
    width: 75%;
    margin-top: 120px;
    .app-title {
      width: 75%;
      .title-header {
        margin-bottom: 70px;
      }
    }
  }
  .app-classes {
    width: 75%;
    .app-title {
      width: 60%;
      .title-header {
        margin-bottom: 60px;
      }
      .title-description {
        margin-bottom: 120px;
      }
    }
    .app-background {
      width: 100%;
      height: 100%;
    }
    .app-block__macbook {
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(121.99deg, #FFA9D8 0%, #DFBCFF 100%);
    }
    .app-img__plane {
      width: 28%;
      right: 2%;
      position: absolute;
    }
    .app-img__frame {
      width: 70%;
      margin: 20px 0;
    }
  }
  .app-feedback {
    width: 75%;
    margin: 160px 0;
  }
  .app-footer {
    margin: 50px 0;
    width: 75%;
    .app-column {
      .app-logo {
        margin-bottom: 20px;
      }
      .app-item:not(:last-child) {
        margin-bottom: 16px;
      }
      .app-item.app-item__header {
        margin-bottom: 30px;
      }
      .app-row {
        margin-top: -4px;
        margin-bottom: 16px;
        .app-icon {
          margin-right: 12px;
        }
      }
    }
  }
}
.app {
  display: flex;
  flex-direction: column;
  align-items: center;
  &-item {
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 17px;
    line-height: 20px;
    color: #333333;
  }
  &-classes {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
  }
  &-fade {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: linear-gradient(180deg, #F6F6F6 0%, #FFFFFF 100%);;
  }
  &-footer {
    display: flex;
    justify-content: space-between;
  }
  &-row {
    display: flex;
  }
}

.app-item__header {
  font-weight: bold;
  font-size: 18px;
  line-height: 21px;
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
