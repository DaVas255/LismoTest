<script setup>
import { ref } from 'vue'

import style from './Main.module.scss'
import Task from '/src/components/task/Task.vue'
import Footer from '@/components/footer/Footer.vue'
import Collapsible from '@/components/collapsible/Collapsible.vue'

const disabled = ref(false)
function warnDisabled() {
  disabled.value = !disabled.value
}
</script>

<template>
  <main :class="style.main">
    <div :class="style.main__background"></div>
    <div :class="style.main__wrapper">
      <div :class="style.main__content">
        <section :class="style.main__header">
          <div :class="style.main__description">
            <div :class="style.main__info">
              <h1 :class="style.main__title">
                Финансовое управление и принципы планирования в здравоохранении
              </h1>
              <p :class="style.main__courseDescr">
                На курсе рассматриваются современные представления об экономике здравоохранения и
                финансовом планировании, в том числе для ведения междисциплинарных проектов в сфере
                медицины, экономики и инженерных технологий.
              </p>
              <p :class="style.main__courseDescr">
                На курсе рассматриваются современные представления об экономике здравоохранения и
                финансовом планировании, в том числе для ведения междисциплинарных проектов в сфере
                медицины, экономики и инженерных технологий.
              </p>
            </div>

            <div :class="style.main__image">
              <img src="/src/assets/png/rec.png" alt="medicine" />
            </div>
          </div>

          <div :class="style.main__teachers">
            <h3 :class="style.main__teacherTitle">Преподаватели курса:</h3>
            <ul :class="style.main__listTeachers">
              <li :class="style.main__listTeacher">
                <img src="/src/assets/teachers/Ellipse 16.png" alt="teacher" />
                А. В. Демакова
              </li>
              <li :class="style.main__listTeacher">
                <img src="/src/assets/teachers/Ellipse 16 (2).png" alt="teacher" />
                А. А. Квасникова
              </li>
              <li :class="style.main__listTeacher">
                <img src="/src/assets/teachers/Ellipse 16 (1).png" alt="teacher" />
                А. А. Красина
              </li>
            </ul>
          </div>
        </section>

        <section :class="style.main__progress">
          <div :class="style.main__commonProgress">
            <div :class="style.main__currentProgress"></div>
          </div>
          71%
        </section>

        <Collapsible label="Общее" closeAll>
          <div :class="style.main__commonContent">
            <h4 :class="style.main__commonSubtitle">Материалы для изучения</h4>
            <ul>
              <li :class="style.main__commonItem">
                <Task typeIcon="zig" typeTask="mustDone"> Список литературы по модулю </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="glossary" typeTask="button"> Глоссарий </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="exercise" typeTask="mustDoneSecond"> Задание </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="folder" typeTask="button" block> Список литературы по модулю </Task>
              </li>

              <li>
                <Task typeIcon="file" typeTask="button"> Список литературы по модулю </Task>
              </li>
            </ul>
          </div>
        </Collapsible>

        <Collapsible
          label="Модуль 1. Объекты интеллектуальной собственности. Интеллектуальные права. Правовая
                охрана объектов интеллектуальной собственности"
        >
          <div :class="style.main__commonContent" v-if="!disabled">
            <h4 :class="style.main__commonSubtitle">Материалы для изучения</h4>
            <ul>
              <li :class="style.main__commonItem">
                <Task typeIcon="zig" typeTask="mustDone"> Список литературы по модулю </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="glossary" typeTask="button"> Глоссарий </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="exercise" typeTask="mustDoneSecond"> Задание </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="folder" typeTask="button" block> Список литературы по модулю </Task>
              </li>

              <li>
                <Task typeIcon="file" typeTask="button"> Список литературы по модулю </Task>
              </li>
            </ul>
          </div>
        </Collapsible>

        <Collapsible
          label="Модуль 2. Объекты интеллектуальной собственности. Интеллектуальные права."
        >
          <div :class="style.main__commonContent">
            <h4 :class="style.main__commonSubtitle">Материалы для изучения</h4>
            <ul>
              <li :class="style.main__commonItem">
                <Task typeIcon="zig" typeTask="mustDone"> Список литературы по модулю </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="file" typeTask="button"> Список литературы по модулю </Task>
              </li>

              <li :class="style.main__commonItem">
                <Task typeIcon="file" typeTask="button" block> Список литературы по модулю </Task>
              </li>
            </ul>
          </div>
        </Collapsible>
      </div>
    </div>
  </main>
  <Footer />
</template>
