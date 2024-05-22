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
    categories: ['Stefan Kraft', 'Janne Ahonen', 'Adam Małysz', 'Gregor Schlierenzauer', 'Simon Ammann', 'Kamil Stoch', 'Thomas Morgenstern', 'Matti Nykänen', 'Jens Weissflog', 'Ryoyu Kobayashi'],
  },
  series: [
    {
      name: 'Miejsce 1.',
      data: [43, 36, 39, 53, 22, 39, 23, 46, 32, 20],
      color: '#eab308',
    },
    {
      name: 'Miejsce 2.',
      data: [35, 44, 27, 20, 31, 22, 30, 22, 22, 25],
      color: '#64748b',
    },
    {
      name: 'Miejsce 3.',
      data: [40, 28, 25, 15, 26, 19, 23, 8, 12, 18],
      color: '#78350f',
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
