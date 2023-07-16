<script setup lang="ts">
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js';
ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale);
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiAccountGroup, mdiCartOutline, mdiChartLine } from '@mdi/js';
import BaseBreadcrumb from '@/components/BaseBreadcrumb.vue';
import BaseHeroTitle from '@/components/BaseHeroTitle.vue';
import BaseCard from '@/components/BaseCard.vue';
import BaseTable from '@/components/BaseTable.vue'
import { ref } from "vue";

const iconAccount = mdiAccountGroup;
const iconCart = mdiCartOutline;
const iconChartLine = mdiChartLine;

const chartData = ref(
  {
    labels: [ 'January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December' ],
    datasets: [
      { 
        label: 'Sales Data',
        data: [30, 35, 40, 45, 50, 55, 65, 60, 55, 50, 60, 55],
        backgroundColor: "#0C86E6",
      }
    ]
  }
);

const chartOptions = ref({
  plugins: {
      title: {
        display: true,
        text: 'Sales Data Chart'
      }
  },
  responsive: true,
  scales: {
      y: {
        min: 0,
        max: 100,
      }
    }
});
</script>

<template>
  <div class="main">
    <BaseBreadcrumb level="Dashboard"/>
    <BaseHeroTitle title="Dashboard"/>
    <section class="columns mt-4">
      <div class="column">
        <BaseCard name="Clients" value="400" :icon="iconAccount" icon-color="has-text-primary"/>
      </div>
      <div class="column">
        <BaseCard name="Sales" value="$7,770" :icon="iconCart" icon-color="has-text-info"/>
      </div>
      <div class="column">
        <BaseCard name="Performance" value="210%" :icon="iconChartLine" icon-color="has-text-primary"/>
      </div>
    </section>
    <section>
      <Bar
        id="my-chart-id"
        :options="chartOptions"
        :data="chartData"
      />
    </section>
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
