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
      name: 'Liczba podiów',
      data: [118, 108, 92, 88, 80, 80, 76, 76, 73, 66],
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
