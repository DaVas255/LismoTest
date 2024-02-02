<script setup>
import style from './Sidebar.module.scss'
import Button from '/src/components/button/Button.vue'
import Contents from '/src/components/contents/Contents.vue'
import { sidebarVisibility } from '@/stores/sideBar.js'

//видимость сайдбара
</script>

<template>
  <aside :class="{ [style.sidebar]: true, [style.sidebarActive]: sidebarVisibility }">
    <Button type="back" />
    <nav>
      <ul>
        <li>
          <Contents />
        </li>
        <li>
          <div :class="style.sidebar__item">
            <img src="/src/assets/svg/people.svg" alt="people" />Участники
          </div>
        </li>
        <li>
          <div :class="style.sidebar__item">
            <img src="/src/assets/svg/timeline.svg" alt="timeline" />Оценки
          </div>
        </li>
      </ul>
    </nav>
  </aside>
</template>
