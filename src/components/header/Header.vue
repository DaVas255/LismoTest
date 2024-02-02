<script setup>
import { ref } from 'vue'

import style from './Header.module.scss'
import { Bars3Icon } from '@heroicons/vue/24/outline'
import { sidebarVisibility } from '@/stores/sideBar.js'

function toggleMenu() {
  sidebarVisibility.value = !sidebarVisibility.value
}
</script>

<template>
  <header :class="style.header">
    <div :class="style.header__logo">
      <a href="#">
        <img src="/src/assets/svg/tusur-logo.svg" alt="logo" />
      </a>
    </div>

    <div :class="style.header__main">
      <div :class="style.header__control">
        <Bars3Icon :class="style.header__burger" @click="toggleMenu" />

        <a href="#">
          <img
            src="/src/assets/svg/notification.svg"
            alt="notification"
            :class="style.header__notification"
          />
        </a>
        <a href="#">
          <img src="/src/assets/svg/chat.svg" alt="chat" :class="style.header__notification" />
        </a>
        <a href="#">
          <img
            src="/src/assets/svg/calendar.svg"
            alt="calendar"
            :class="style.header__notification"
          />
        </a>
      </div>

      <div :class="style.header__profile">
        <div :class="style.header__user">
          <img
            src="/src/assets/svg/profile-default-icon.svg"
            alt="profile-icon"
            :class="style.header__avatar"
          />
          <a href="#">Иван Иванов</a>
        </div>

        <button :class="style.header__exit">Выход</button>
      </div>
    </div>
  </header>
</template>
