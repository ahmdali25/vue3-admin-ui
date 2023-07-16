<script setup lang="ts">
const props = defineProps({
  title: String,
});
</script>

<template>
  <section class="hero is-small">
    <div class="hero-body">
      <p class="title">
        {{ props.title }}
      </p>
  	</div>
  </section>
</template>

<style scoped>
.hero {
  background-color: #FFFFFF;
}
</style>