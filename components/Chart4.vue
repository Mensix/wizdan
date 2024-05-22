<script setup lang="ts">
import { reactive } from 'vue'
import type { ApexOptions } from 'apexcharts'
import VueApexCharts from 'vue3-apexcharts'

const chart = reactive<ApexOptions>({
  chart: {
    id: 'vuechart-example',
    toolbar: {
      show: false,
    },
  },
  grid: {
    padding: {
      left: 32,
      right: 32,
    },
  },
  xaxis: {
    categories: ['Austria', 'Norwegia', 'Niemcy/NRD/RFN', 'Finlandia', 'Polska', 'Japonia', 'Słowenia/Jugosławia', 'Czechy/Czechosłowacja', 'Szwajcaria', 'Kanada', 'Szwecja', 'Włochy', 'USA', 'Francja', 'Rosja'],
  },
  series: [
    {
      name: 'Liczba zwycięstw',
      data: [324, 184, 181, 166, 107, 102, 97, 36, 33, 14, 7, 7, 3, 1, 1],
      color: '#eab308',
    },
  ],
  dataLabels: {
    style: {
      fontSize: '12px',
      colors: ['#000000'],
    },
  },
})
</script>

<template>
  <VueApexCharts type="bar" :options="chart" :series="chart.series" height="60%" width="90%" />
</template>
