<script setup>
import style from './SubjectItem.module.scss'
</script>

<template>
  <div :class="style.item">
    <img src="/src/assets/svg/Frame2.svg" alt="T" :style="{ marginRight: '20px' }" />
    <slot></slot>
    <img src="/src/assets/svg/Frame1.svg" alt="A" :style="{ marginLeft: 'auto' }" />
  </div>
</template>
