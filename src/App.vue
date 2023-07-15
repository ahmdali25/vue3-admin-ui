<script setup lang="ts">
import TheNavbar from './components/TheNavbar.vue';
import TheSidebar from './components/TheSidebar.vue';
import { RouterView } from 'vue-router';
</script>

<template>
  <TheNavbar/>
  <section>
    <TheSidebar/>
    <RouterView/>
  </section>
</template>

<style>
main {
  background-color: #F8F8F8;
  padding: 90px 1em 2em 260px;
}
</style>
