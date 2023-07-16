<script setup lang="ts">
import TheNavbar from './components/TheNavbar.vue';
import TheSidebar from './components/TheSidebar.vue';
import TheFooter from './components/TheFooter.vue';
import { RouterView } from 'vue-router';
</script>

<template>
  <TheNavbar/>
  <TheSidebar/>
  <RouterView/>
  <TheFooter/>
</template>

<style scoped>
.main {
  background-color: #F8F8F8;
  padding: 90px 1em 2em 260px;
}
</style>
