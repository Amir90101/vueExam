<template>
  <div>
    <h2>{{ currentLesson.title }}</h2>
    <span class="time">{{ currentLesson.time }}</span>
    <span>{{ currentLesson.name }} {{ currentLesson.surname }} {{ currentLesson.father }}</span
    ><br />
    <p>{{ currentLesson.discription }}</p>

    <table>
      <tr>
        <td>Students Name</td>
      </tr>
      <table-students v-for="student in students" :key="student" :name="student"></table-students>
    </table>
    
    <li>
      <router-link :to="{ name: 'LessonPage' }">Lessons</router-link>
    </li>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import type { Lesson } from '@/types/lesson'
import TableStudents from '@/components/TableStudents.vue'
interface Props {
  id: string
}
const props = defineProps<Props>()
const currentLesson = ref<Lesson>({} as Lesson)
const students = ref<string[]>([])
onMounted(() => {
  const lessons = JSON.parse(localStorage.getItem('LessonsData') as string)
  lessons.forEach((item: any) => {
    if (item.id == props.id) currentLesson.value = item
  })
  students.value = Object.keys(currentLesson.value.students)
  console.log(students)
})

</script>

<style scoped></style>
