<script setup>
import style from './Task.module.scss'
import Button from '@/components/button/Button.vue'

defineProps({
  typeIcon: String,
  typeTask: String,
  block: Boolean
})
</script>

<template>
  <div :class="style.task">
    <div :class="style.task__content">
      <div :class="style.task__title">
        <img
          src="/src/assets/iconElements/1.png"
          alt="icon"
          v-if="typeIcon === 'zig'"
          :class="style.task__icon"
        />
        <img
          src="/src/assets/iconElements/2.png"
          alt="icon"
          v-if="typeIcon === 'glossary'"
          :class="style.task__icon"
        />
        <img
          src="/src/assets/iconElements/3.png"
          alt="icon"
          v-if="typeIcon === 'exercise'"
          :class="style.task__icon"
        />
        <img
          src="/src/assets/iconElements/4.png"
          alt="icon"
          v-if="typeIcon === 'folder'"
          :class="style.task__icon"
        />
        <img
          src="/src/assets/iconElements/5.png"
          alt="icon"
          v-if="typeIcon === 'file'"
          :class="style.task__icon"
        />
        <slot></slot>
      </div>

      <div :class="style.task__type">
        <Button v-if="typeTask === 'button'" type="mark" />

        <div v-if="typeTask === 'mustDone'" :class="style.task__typeMust">
          <span :class="style.task__accentText">Надо сделать:</span> Получить оценку
        </div>

        <div v-if="typeTask === 'mustDoneSecond'" :class="style.task__accentTask">
          <div :class="style.task__typeMust">
            <span :class="style.task__accentText">Надо сделать:</span> Получить оценку
          </div>
          <div :class="[style.task__typeMust, style.task__typeMustDone]">
            <img src="/src/assets/svg/done.svg" alt="done" :class="style.task__iconDone" />
            Выполнено: Просмотреть
          </div>
          <div :class="[style.task__typeMust, style.task__typeMustDone]">
            <img
              src="/src/assets/svg/done.svg"
              alt="done"
              :class="style.task__iconDone"
            />Выполнено: Получить оценку
          </div>
        </div>
      </div>
    </div>

    <div :class="style.task__block" v-if="block">
      <img src="/src/assets/svg/lock_open.svg" alt="lock" :class="style.task__blockIcon" />
      <p>
        Недоступно, пока не выполнено: Элемент курса <br />
        <span :class="style.task__accentText">Задание</span> должен быть отмечен как выполненный
      </p>
    </div>
  </div>
</template>
