<script setup>
import { ref } from 'vue'
import style from './Collapsible.module.scss'

const open = ref(false)

function openAll() {
  open.value = !open.value
}
defineProps({
  label: String,
  closeAll: Boolean
})
</script>

<template>
  <section :class="style.collapsible">
    <div :class="style.collapsible__header">
      <div :class="style.collapsible__headerArrow">
        <img
          src="/src/assets/svg/keyboard_arrow_right.svg"
          alt="arrow right"
          @click="open = !open"
          v-if="!open"
        />
        <img
          src="/src/assets/svg/keyboard_arrow_bottom.svg"
          alt="arrow bottom"
          @click="open = !open"
          v-if="open"
        />
        <h3 :class="style.collapsible__commonTitleName">{{ label }}</h3>
      </div>
      <span :class="style.collapsible__commonCollapse" v-if="closeAll" @click="open = !open"
        >Свернуть всё</span
      >
    </div>

    <slot v-if="open"></slot>
  </section>
</template>
