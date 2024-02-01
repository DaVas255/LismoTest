<script setup>
import style from './Sidebar.module.scss'
import Button from '/src/components/button/Button.vue'
import Contents from '/src/components/contents/Contents.vue'
</script>

<template>
  <aside :class="style.sidebar">
    <Button type="back" />
    <Contents />
    <div :class="style.sidebar__item">
      <img src="/src/assets/svg/people.svg" alt="people" />Участники
    </div>
    <div :class="style.sidebar__item">
      <img src="/src/assets/svg/timeline.svg" alt="timeline" />Оценки
    </div>
  </aside>
</template>
