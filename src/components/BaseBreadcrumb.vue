<script setup lang="ts">
const props = defineProps({
  level: String,
});
</script>

<template>
    <nav class="breadcrumb is-medium" aria-label="breadcrumbs">
        <ul>
            <li><a href="#">Admin</a></li>
            <li class="level is-active"><a href="#" aria-current="page">{{ props.level }}</a></li>
        </ul>
    </nav>
</template>

<style scoped>
a {
    color: #000000;
    cursor: default !important;
}
.level {
    font-weight: 900;
    color: #242424;
}
</style>