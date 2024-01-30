<script setup>
import { ref } from 'vue'
import style from './Contents.module.scss'

const disabled = ref(false)
function warnDisabled() {
  disabled.value = !disabled.value
}
</script>

<template>
  <div :class="style.contents">
    <div :class="style.contents__title" @click="warnDisabled">
      <img src="/src/assets/svg/contents.svg" alt="contents" />
      Содержание
      <img src="/src/assets/svg/keyboard_arrow_right.svg" alt="arrow right" v-if="!disabled" />
      <img src="/src/assets/svg/keyboard_arrow_bottom.svg" alt="arrow right" v-if="disabled" />
    </div>

    <div v-if="disabled">This feature is disabled!</div>
  </div>
</template>
