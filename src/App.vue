<script>
import UiButton from "./components/UiButton.vue";

export default {
  components: {UiButton},
  data() {
    return {
      buttonColor: '',
      buttonSize: 'md',
      buttonActive: true,
      buttonLoading: false,
      buttonStretch: false,
      buttonIcon: true,
      buttonIconVariant: '',
    }
  },
}
</script>

<template>
  <div class="container">
    <div class="card_center">
      <h1>Button create</h1>
      <div class="form-control">
        <form action="">
          <label for="">Цвет:</label>
          <label for="">
            <input type="radio" name="color" value="black" v-model="buttonColor">
            Black
          </label>
          <label for="">
            <input type="radio" name="color" value="red" v-model="buttonColor">
            Red
          </label>
          <label for="">
            <input type="radio" name="color" value="gray" v-model="buttonColor">
            Gray
          </label>
          <hr>

          <label for="">Размер:</label>
          <label for="">
            <input type="radio" name="size" value="xs" v-model="buttonSize">
            XS
          </label>
          <label for="">
            <input type="radio" name="size" value="md" v-model="buttonSize">
            MD
          </label>
          <label for="">
            <input type="radio" name="size" value="lg" v-model="buttonSize">
            LG
          </label>
          <hr>

          <label for="">Активна:</label>
          <label for="">
            True
            <input type="radio" name="active" :value="true" v-model="buttonActive">
          </label>
          <label for="">
            False
            <input type="radio" name="active" :value="false" v-model="buttonActive">
          </label>
          <hr>

          <label for="">Загрузка:</label>
          <label for="">
            True
            <input type="radio" name="loading" :value="true" v-model="buttonLoading">
          </label>
          <label for="">
            False
            <input type="radio" name="loading" :value="false" v-model="buttonLoading">
          </label>
          <hr>

          <label for="">Вся ширина:</label>
          <label for="">
            True
            <input type="radio" name="stretch" :value="true" v-model="buttonStretch">
          </label>
          <label for="">
            False
            <input type="radio" name="stretch" :value="false" v-model="buttonStretch">
          </label>
          <hr>

          <label for="">Иконка:</label>
          <label for="">
            True
            <input type="radio" name="icon" :value="true" v-model="buttonIcon">
          </label>
          <label for="">
            False
            <input type="radio" name="icon" :value="false" v-model="buttonIcon">
          </label>
          <hr>
          <label for="">Иконка:</label>
          <label for="">
            left
            <input type="radio" name="icon-variant" value="left" v-model="buttonIconVariant">
          </label>
          <label for="">
            right
            <input type="radio" name="icon-variant" value="right" v-model="buttonIconVariant">
          </label>
          <label for="">
            Disable
            <input type="radio" name="icon-variant" :value="null" v-model="buttonIconVariant">
          </label>
          <hr>
        </form>
      </div>
      <ui-button
          :text="'Add'"
          :variant="buttonColor"
          :active="buttonActive"
          :loading="buttonLoading"
          :stretch="buttonStretch"
          :size="buttonSize"
          :icon-variant="buttonIconVariant"
      >
        <template #left >
          <i class="icon">X</i>
        </template>
        <template #right >
          <i class="icon">X</i>
        </template>
      </ui-button>
    </div>
  </div>
<!--  <div class="container">-->
  <!--    <div class="card">-->
  <!--      <h1>UI Button variant</h1>-->
  <!--      <ui-button-->
  <!--          :text="'Add'"-->
  <!--          :variant="'black'"-->
  <!--          :is-active="true"-->
  <!--          :is-loading="false"-->
  <!--          :is-stretch="false"-->
  <!--          :size="'xs'"-->
  <!--      >-->

  <!--        &lt;!&ndash;  Можно ли сделать при передаче пустой строки ``,-->
  <!--              чтобы размер по дефолту был md, в пропсе-->
  <!--               default не работает. Или в разработке не будут передавать-->
  <!--               пустые строки, вместо параметра?&ndash;&gt;-->
  <!--        <template #left v-if="true"> &lt;!&ndash; Надо ли связывать с isLoading &ndash;&gt;-->
  <!--          &lt;!&ndash;          <img class="icon" src="https://play.vuejs.org/logo.svg" alt="">&ndash;&gt;-->
  <!--          &lt;!&ndash;           Сделал костыль, через i-->
  <!--                         (Сюда можно, через копи-пасту-->
  <!--                         вставить иконку 🔍, вместо Х)-->
  <!--                         Не разобрался, как с выбором размера кноки,-->
  <!--                         изменялась и иконка через img&ndash;&gt;-->
  <!--          <i class="icon">X</i>-->
  <!--        </template>-->
  <!--        &lt;!&ndash;        Смотря где нужна иконка слева или справа   &ndash;&gt;-->
  <!--        <template #right v-if="false">-->
  <!--          <i class="icon">X</i>-->
  <!--        </template>-->
</template>

<style scoped>

body {
  display: flex;
  justify-content: space-between;
}

.icon {
  margin: 0 8px;
}

button {
  margin-bottom: 10px;
}
</style>
