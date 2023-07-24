<template>
  <div>
    <div class="nav__lessons">
      <li>
        <router-link :to="{ name: 'LessonAdd' }">created lessons</router-link>
      </li>
    </div>
    <lesson-card
      v-for="lesson in lessons"
      :key="lesson.id"
      :lesson-id="lesson.id"
      :name="lesson.name"
      :surname="lesson.surname"
      :father="lesson.father"
      :title="lesson.title"
      :time="lesson.time"
    ></lesson-card>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import LessonCard from '@/components/LessonCard.vue'
const data = []
onMounted(() => {
  if (!localStorage.getItem('LessonsData')) {
    localStorage.setItem('LessonsData', JSON.stringify(data))
  }
})
const lessons = ref(JSON.parse(localStorage.getItem('LessonsData') as string))
</script>

<style scoped>
.nav__lessons {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid black;
  padding: 20px;
}
</style>
