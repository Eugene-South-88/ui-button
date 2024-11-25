<script>
import UiButton from "./components/UiButton.vue";

export default {
  components: {UiButton},
  data() {
    return {
    }
  }
}
</script>

<template>
    <div class="card">
      <h1>UI Button</h1>
      <ui-button
          :text="'Add'"
          :variant="'black'"
          :is-active="true"
          :is-loading="false"
          :is-stretch="true"
          :size="'xs'"
      >
        <!--  Можно ли сделать при передаче пустой строки ``,
              чтобы размер по дефолту был md, в пропсе
               default не работает. Или в разработке не будут передавать
               пустые строки, вместо параметра?-->
        <template #left v-if="true" > <!-- Надо ли связывать с isLoading -->
<!--          <img class="icon" src="https://play.vuejs.org/logo.svg" alt="">-->
<!--           Сделал костыль, через i
               (Сюда можно, через копи-пасту
               вставить иконку 🔍, вместо Х)
               Не разобрался, как с выбором размера кноки,
               изменялась и иконка через img-->
          <i class="icon">X</i>
        </template>
<!--        Смотря где нужна иконка слева или справа   -->
        <template #right v-if="false">
          <i class="icon">X</i>
        </template>

      </ui-button>
    </div>
</template>

<style scoped>

.icon {
  margin: 0 8px;
}
</style>
