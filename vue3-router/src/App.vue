<script setup>
import { RouterLink, RouterView } from 'vue-router'
import navbar from './components/navbar.vue'
import TheHeader from './components/TheHeader.vue';
import TheSideBar from './components/TheSideBar.vue';
import TheFooter from './components/TheFooter.vue';
</script>

<template>

  <TheHeader />
  <RouterView />
  <navbar />
  <TheSideBar />
  <TheFooter />

</template>

<style scoped>

</style>
