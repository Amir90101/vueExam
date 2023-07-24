<template>

  <div>
    <h1>Home page</h1>
    <ul>

      <li>
        <router-link :to="{ name: 'UserPage' }">Users</router-link>
      </li>
      <li>
        <router-link :to="{ name: 'LessonPage' }">Lessons</router-link>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>

div {
  width:1020px;
  height: 500px;
  background-color :aqua;


}
</style>
