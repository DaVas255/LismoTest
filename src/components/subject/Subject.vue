<script setup>
import style from './Subject.module.scss'
import SubjectItem from '../subject-item/SubjectItem.vue'
import { ref } from 'vue'

const subjects = ['Задание', 'Лекция', 'Тест', 'Форум']

const disabled = ref(false)
function warnDisabled() {
  disabled.value = !disabled.value
}
</script>

<template>
  <div :class="style.subject">
    <h3 :class="style.subject__title" @click="warnDisabled">
      <slot></slot>
      <img src="/src/assets/svg/keyboard_arrow_right.svg" alt="arrow right" v-if="!disabled" />
      <img src="/src/assets/svg/keyboard_arrow_bottom.svg" alt="arrow right" v-if="disabled" />
    </h3>

    <ul v-if="disabled">
      <li v-for="i in subjects" :key="i">
        <SubjectItem> {{ i }} </SubjectItem>
      </li>
    </ul>
  </div>
</template>
