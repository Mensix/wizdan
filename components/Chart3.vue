<script setup lang="ts">
import { ref } from 'vue'
import { Bar } from 'vue-chartjs'
import { BarElement, CategoryScale, Chart as ChartJS, Legend, LinearScale, Title, Tooltip } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

const chartData = ref({
  labels: ['Stefan Kraft', 'Janne Ahonen', 'Adam Małysz', 'Gregor Schlierenzauer', 'Simon Ammann', 'Kamil Stoch', 'Thomas Morgenstern', 'Matti Nykänen', 'Jens Weissflog', 'Ryoyu Kobayashi'],
  datasets: [
    {
      label: 'Miejsce 1.',
      backgroundColor: '#eab308',
      data: [43, 36, 39, 53, 22, 39, 23, 46, 32, 20],
    },
    {
      label: 'Miejsce 2.',
      backgroundColor: '#64748b',
      data: [35, 44, 27, 20, 31, 22, 30, 22, 22, 25],
    },
    {
      label: 'Miejsce 3.',
      backgroundColor: '#78350f',
      data: [40, 28, 25, 15, 26, 19, 23, 8, 12, 18],
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
    :data="chartData"
  />
</template>
