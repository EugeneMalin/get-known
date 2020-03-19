/**
 * Компонент для приглашения посетителя
 * Отображает заголовок с полем для ввода email, а так же линком на политику конфиденциальности
 */
<template>
  <div class="invitation" :class="{ 'invitation__main': isMain }">
      <div class="invitation-title">
          {{ title }}
      </div>
      <div class="invitation-field">
          <a-input-group compact class="invitation-inputgroup">
              <a-input style="width: calc(100% - 154px)" placeholder="email" defaultValue="mail@mail.ru" class="invitation-input"/>
              <a-button style="width: 154px" type="primary" class="invitation-button">Получить</a-button>
          </a-input-group>
      </div>
      <div class="invitation-suggestions">
          Мы заботимся о персональных данных. <span class="invitation-suglink">Политика конфиденциальности</span>
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

<style lang="less">
    .invitation {
        .invitation-title {
            width: 45%;
            margin-bottom: 46px;
        }
        .invitation-field {
            margin-bottom: 15px;
        }
    }

    .invitation {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        
        &-title {
            font-family: Roboto;
            font-style: normal;
            font-weight: 900;
            font-size: 34px;
            line-height: 40px;
            text-align: center;
            color: #000000;
        }
        &-input {
            justify-content: center;
            display: flex;
        }
        &-button {
            width: 154px;
            background: #374CBA;
            border-radius: 0px 8px 8px 0px;
        }
        &-suggestions {
            font-family: Roboto;
            font-style: normal;
            font-weight: normal;
            font-size: 13px;
            text-align: center;
            color: #A0A0A9;
        }
        &-suglink {
            text-decoration: underline;
        }
        &-field {
            width: 380px;
        }
        &-inputgroup {
            display: flex;
        }
        &.invitation__main {
            background: linear-gradient(99.63deg, #5068EF 0%, #7A59F6 97.61%);

            .invitation-title {
                color: #FFFFFF;
                font-size: 58px;
                line-height: 68px;
                margin-bottom: 60px;
            }
            .invitation-field {
                margin-bottom: 18px;
            }
        }
    }
</style>