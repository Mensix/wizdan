<script setup lang="ts">
import { reactive } from 'vue'
import { Bar } from 'vue-chartjs'
import { BarElement, CategoryScale, Chart as ChartJS, Legend, LinearScale, Title, Tooltip } from 'chart.js'
import type { Chart, ChartData } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

const chartData = reactive({
  labels: ['Gregor Schlierenzauer', 'Matti Nykänen', 'Stefan Kraft', 'Adam Małysz', 'Kamil Stoch', 'Janne Ahonen', 'Jens Weissflog', 'Ryoyu Kobayashi', 'Martin Schmitt', 'Andreas Felder', 'Halvor Egner Granerud'],
  datasets: [
    {
      label: 'Najwięcej zwycięstw w konkursach PŚ',
      backgroundColor: '#eab308',
      data: [53, 46, 43, 39, 39, 36, 33, 32, 28, 25, 25],
    },
  ],
  options: {
    responsive: true,
  },
})
</script>

<template>
  <Bar
    id="my-chart-id"
    :options="chartOptions"
    :data="chartData"
  />
</template>
