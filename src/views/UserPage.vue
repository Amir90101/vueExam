<template>
    <div>
        <h1>Users Page</h1>
        <li>
        <router-link :to="{ name: 'HomePage' }">Главная</router-link>
      </li>
        <router-view></router-view>
    </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
</style>