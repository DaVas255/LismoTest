<script setup>
import style from './Button.module.scss'
import Button from '@/components/button/Button.vue'
import { ref } from 'vue'

const buttonType = ref(false)
function buttonChange() {
  buttonType.value = !buttonType.value
}

const props = defineProps({
  type: String
})
</script>

<template>
  <button v-if="type == 'back'" :class="style.button">
    <img src="/src/assets/svg/arrow.svg" alt="" />Назад к списку курсов
  </button>

  <div v-else-if="type == 'mark'">
    <button :class="style.mark" @click="buttonChange" v-if="!buttonType">
      Отметить как выполненный
    </button>

    <button :class="[style.mark, style.mark_done]" @click="buttonChange" v-if="buttonType">
      <img src="/src/assets/svg/done.svg" alt="done" />
      Выполнено
    </button>
  </div>
</template>
