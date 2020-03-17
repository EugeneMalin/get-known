/**
 * Компонент для приглашения посетителя
 * Отображает заголовок с полем для ввода email, а так же линком на политику конфиденциальности
 */
<template>
  <div class="invitation" :class="{ 'invitation__main': isMain }">
      <div class="invitation-title">
          {{ title }}
      </div>
    <a-input-group compact class="invitation-inputgroup">
        <a-input style="width: 20%" placeholder="email" defaultValue="mail@mail.ru" class="invitation-input"/>
        <a-button style="width: 154px" type="primary" class="invitation-button">Получить</a-button>
    </a-input-group>
    <div class="invitation-suggestions">
        Мы заботимся о персональных данных. <a-button type="link" class="invitation-suglink">Политика конфиденциальности</a-button>
    </div>
  </div>
</template>

<script>
export default {
    props: {
        title: String,
        isMain: Boolean
    }
}
</script>

<style>
    .invitation {
        display: flex;
        flex-direction: column;
        width: 100%;
    }
    .invitation-title {
        font-family: Roboto;
        font-style: normal;
        font-weight: 900;
        font-size: 34px;
        line-height: 40px;
        text-align: center;
        color: #000000;
    }
    .invitation-input {
        justify-content: center;
        display: flex;
    }
    .invitation-button {
        width: 154px;
        background: #374CBA;
        border-radius: 0px 8px 8px 0px;
    }
    .invitation-suggestions {
        font-family: Roboto;
        font-style: normal;
        font-weight: normal;
        font-size: 13px;
        text-align: center;
        color: #A0A0A9;
    }

    .invitation__main {
        background-color: #324BC0;
    }
</style>