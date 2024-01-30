<script setup>
import style from './Button.module.scss'
const props = defineProps({
  type: String
})
</script>

<template>
  <button v-if="type == 'back'" :class="style.button">
    <img src="/src/assets/svg/arrow.svg" alt="" />Назад к списку курсов
  </button>

  <button v-else-if="type == 'mark'" :class="style.button">Отметить как выполненный</button>
</template>
