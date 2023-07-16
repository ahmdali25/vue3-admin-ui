<script setup lang="ts">
import BaseTable from '@/components/BaseTable.vue';
import BaseBreadcrumb from '@/components/BaseBreadcrumb.vue';
import BaseHeroTitle from '@/components/BaseHeroTitle.vue';
</script>

<template>
  <div class="main">
    <BaseBreadcrumb level="Tables"/>
    <BaseHeroTitle title="Tables"/>
    <section class="card mt-5">
      <header class="card-header">
        <p class="card-header-title">
          Clients Data
        </p>
      </header>
      <div class="card-content">
        <BaseTable />
      </div>
    </section>
  </div>
</template>