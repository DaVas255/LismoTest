<script setup>
import style from './Main.module.scss'
import Button from '/src/components/button/Button.vue'
</script>

<template>
  <div :class="style.main">
    <main :class="style.main__content">Content of the main area</main>
  </div>
</template>
