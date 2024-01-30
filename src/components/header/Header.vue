<script setup>
import style from './Header.module.scss'
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
        <a href="#">
          <img src="/src/assets/svg/notification.svg" alt="notification" />
        </a>
        <a href="#">
          <img src="/src/assets/svg/chat.svg" alt="chat" />
        </a>
        <a href="#">
          <img src="/src/assets/svg/calendar.svg" alt="calendar" />
        </a>
      </div>

      <div :class="style.header__profile">
        <div :class="style.header__user">
          <img src="/src/assets/svg/profile-default-icon.svg" alt="profile-icon" />
          <a href="#">Иван Иванов</a>
        </div>

        <button :class="style.header__exit">Выход</button>
      </div>
    </div>
  </header>
</template>
