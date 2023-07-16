<script setup lang="ts">
import SvgIcon from '@jamescoyle/vue-icon';

interface Props {
  name?: string,
  value?: string,
  icon?: string,
  iconColor?: string,
}

const props = defineProps<Props>()
</script>

<template>
  <div class="card p-5">
    <div class="card-content">
      <div class="is-flex is-justify-content-space-around is-align-items-center">
        <div class="t">
          <p class="subtitle is-5">{{ props.name }}</p>
          <p class="title is-3">{{ props.value }}</p>
        </div>
        <div>
          <svg-icon class="icon is-large" :class="props.iconColor" type="mdi" :path="props.icon"></svg-icon>
        </div>
      </div>
    </div>
  </div>
</template>