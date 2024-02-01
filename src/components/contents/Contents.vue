<script setup>
import { ref } from 'vue'
import style from './Contents.module.scss'
import Subject from '../subject/Subject.vue'

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

    <div :class="style.contents__list" v-if="disabled">
      <Subject> Тема 1. Основы технологии производства ЭС </Subject>
      <Subject> Тема 2. Моделирование бизнес-процессов предметной области </Subject>
      <Subject> Тема 3. Модели разработки программного продукта </Subject>
    </div>
  </div>
</template>
