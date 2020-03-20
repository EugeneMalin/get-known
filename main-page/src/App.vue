<template>
  <div class="app">
    <Cover class="app-cover"/>
    <Invitation class="app-invitation" title="Хотите получить бесплатный живой урок?" :isMain="false"/>
    <div class="app-fade">
      <div class="app-advantage">
        <Title class="app-title" header="Удобная платформа для образования" description="Для простоты изучения мы разработали для Вас личный кабинет ученика!" />
        <div class="app-grid">
          <div class="app-griditem app-griditem__small-square" slot="renderItem" v-for="item in advantages" :key="item.key">
            <img :src=item.icon>
            <div class="app-griddescription">{{item.description}}</div>
          </div>
        </div>
      </div>
      <div class="app-courses">
        <Title class="app-title" header="Большой выбор курсов с живыми преподавателями"/>
        
      </div>
    </div>
    <div class="app-fade">
      <div class="app-teachers">
        <Title class="app-title" header="Познакомьтесь с теми, кто будет ваc учить"/>
        <div class="app-grid">
          <div class="app-griditem app-griditem__teacher" slot="renderItem" v-for="item in teachers" :key="item.key">
            <div class="app-list">
              <div class="app-listitem" v-for="row in item.rows" :key="row">{{row}}</div>
            </div>
            <div class="app-person">
              <img class="app-personphoto" :src=item.photo>
              <div class="app-name">
                {{item.name}}
              </div>
              <div class="app-link">Слушать<img class="app-icon" src="@/assets/headphone.png"></div>
            </div>
          </div>
        </div>
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

import teacher from '@/assets/teacher.png'
import teacher1 from '@/assets/teacher1.png'
import teacher2 from '@/assets/teacher2.png'

import computer from '@/assets/computer.svg'
import rising from '@/assets/rising.svg'
import student from '@/assets/student.svg'
import time from '@/assets/time.svg'
import tea from '@/assets/tea.svg'

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

const teachers = [
  {
    key: 0,
    photo: teacher,
    rows: [
      'Китайский язык с нуля и для начинающих',
      'Детский курс китайского языка от 5 до 12 лет',
      'Курс китайского языка для продвинутых и продолжающих'
    ],
    name: 'Ольга Ненахова'
  },
  {
    key: 1,
    photo: teacher1,
    rows: [
      'Китайский язык с нуля и для начинающих',
      'Детский курс китайского языка от 5 до 12 лет',
      'Курс китайского языка для продвинутых и продолжающих'
    ],
    name: 'Света Иванова'
  },
  {
    key: 2,
    photo: teacher2,
    rows: [
      'Китайский язык с нуля и для начинающих',
      'Детский курс китайского языка от 5 до 12 лет',
      'Курс китайского языка для продвинутых и продолжающих'
    ],
    name: 'Наталья Афонина'
  }
]
const advantages = [
  {
    key: 0,
    icon: student,
    description: 'Домашнее задание после каждого урока'
  },
  {
    key: 1,
    icon: time,
    description: 'Вы сами выбираете вермя занятий'
  },
  {
    key: 2,
    icon: tea,
    description: 'Бесплатный перенос и отмена занятий'
  },
  {
    key: 3,
    icon: rising,
    description: 'Пройденные уроки хранятся для повтора'
  },
  {
    key: 4,
    icon: computer,
    description: 'Весь материал в личном кабинете'
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
      feedbackPoints,
      advantages,
      teachers
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
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    margin-top: 120px;
    .app-title {
      display: flex;
      align-items: center;
      width: 75%;
      .title-header {
        width: 65%;
        margin-bottom: 60px;
      }
      .title-description {
        margin-bottom: 40px;
      }
    }
  }

  .app-courses {
    margin-top: 110px;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 75%;
    margin-top: 120px;
    .app-title {
      width: 80%;
      .title-header {
        margin-bottom: 70px;
      }
    }
  }
  .app-getinvitation {
    height: 486px;
  }
  .app-teachers {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    margin-top: 120px;
    margin-bottom: 200px;
    .app-title {
      width: 56.25%;
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
  &-grid {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    justify-content: space-between;
    padding: 0 5%;
  }
  &-griddescription {
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 15px;
    line-height: 18px;
    text-align: center;
    margin-top: 25px;
    color: #000000;
  }
  &-griditem {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 28px;
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
  &-listitem {
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 170%;
    color: #545464;
  }
  &-personphoto {
    width: 60px;
    height: 60px;
    margin-bottom: 28px;
  }
  &-person {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  &-link {
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 18px;
    line-height: 21px;
    /* identical to box height */

    text-align: center;

    color: #5168EF;
  }
  &-icon {
     margin: 6px;
  }
  &-name {
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 24px;
    line-height: 28px;
    text-align: center;
    margin-bottom: 6px;
    color: #000000;
  }
}

.app-item__header {
  font-weight: bold;
  font-size: 18px;
  line-height: 21px;
}
.app-griditem__small-square {
  border: 1px solid #E2E2E2;
  box-sizing: border-box;
  border-radius: 26px;
  width: 15vw;
  height: 15vw;
  min-width: 170px;
  min-height: 170px;
  margin: 16px;
}
.app-griditem__teacher {
  border: 1px solid #DDDFE5;
  box-sizing: border-box;
  border-radius: 10px;
  width: 24vw;
  height: 36vw;
  min-width: 180px;
  min-height: 270px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
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
