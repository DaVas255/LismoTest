<script setup>
import style from './Sidebar.module.scss'
import Button from '/src/components/button/Button.vue'
import Contents from '/src/components/contents/Contents.vue'
</script>

<template>
  <aside :class="style.sidebar">
    <Button type="back" />
    <Contents />
  </aside>
</template>
