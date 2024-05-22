<script setup lang="ts">
import type { ApexOptions } from 'apexcharts'
import { reactive } from 'vue'
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
      left: 64,
      right: 64,
    },
  },
  xaxis: {
    categories: ['Gregor Schlierenzauer', 'Matti Nykänen', 'Stefan Kraft', 'Adam Małysz', 'Kamil Stoch', 'Janne Ahonen', 'Jens Weissflog', 'Ryoyu Kobayashi', 'Martin Schmitt', 'Andreas Felder', 'Halvor Egner Granerud'],
  },
  series: [
    {
      name: 'Liczba zwycięstw',
      color: '#eab308',
      data: [53, 46, 43, 39, 39, 36, 33, 32, 28, 25, 25],
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
  <VueApexCharts type="bar" :options="chart" :series="chart.series" height="90%" width="90%" />
</template>
