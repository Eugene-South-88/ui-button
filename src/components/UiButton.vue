<template>
  <button
      :disabled="!active"
      :class="[buttonSize, variant]"
      :style="{width: stretch? '100%': '',}"
  >
    <template v-if="loading===false && iconVariant==='left' ">
      <slot name="left"/>
    </template>
    {{ loading ? '' : text }}
    <template v-if="loading===false && iconVariant==='right' ">
      <slot name="right"/>
    </template>
    <span v-show="loading" class="loader"></span>
  </button>
</template>

<script>
export default {
  props: {
    iconVariant:{
      type: String,
      default: '',
    },
    text: String,
    variant: {
      type: String,
      default: 'gray',
      validate(value) {
        return ['', 'black', 'gray', 'red']
      }
    },
    active: {
      type: Boolean,
      default: true,
    },
    loading: {
      type: Boolean,
      default: false,
    },
    stretch: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: 'md',
      validator(value) {
        return ['xs', 'md', 'lg'].includes(value)
      }
    }
  },
  computed: {
    buttonSize() {
      return {
        xs: this.size === 'xs',
        md: this.size === 'md',
        lg: this.size === 'lg',
      }
    }
  }
}
</script>
<!--Не понял, как до ума одной строчко довести disabled,
 у меня при блокировке цвета с класса black,red,gray
превосходствуют над цветовыми disabled, хотя cursor меняеяется -->
<style scoped>

button:disabled{
  opacity: 0.3;
  cursor: default;
}

button {
  border-radius: 12px;
  cursor: pointer;
  align-items: center;
  display: inline-flex;
  justify-content: center;
}

button.xs {
  padding: 8px 16px;
  font-size: 12px;
  line-height: 1.2;
}

button.md {
  padding: 12px 20px;
  font-size: 16px;
  line-height: 1.5;
}

button.lg {
  padding: 16px 28px;
  font-size: 20px;
  line-height: 1.8;
}

button.black {
  background-color: #1e1e2f;
  color: white;
}

button.red {
  background-color: red;
  color: white;
}

button.gray {
  background-color: #A3A3B5;
  color: black;
}

button span {
  margin: 0 5px;
  display: flex;
}

.loader {
  margin: 0 auto;
  width: 16px;
  height: 16px;
  border: 3px solid rgba(255, 255, 255, 0.3);
  border-top: 3px solid white;
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>