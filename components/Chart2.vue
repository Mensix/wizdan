<script setup lang="ts">
import { reactive } from 'vue'
import { Bar } from 'vue-chartjs'
import { BarElement, CategoryScale, Chart as ChartJS, Legend, LinearScale, Title, Tooltip } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

const chartData = reactive({
  labels: ['Stefan Kraft', 'Janne Ahonen', 'Adam Małysz', 'Gregor Schlierenzauer', 'Simon Ammann', 'Kamil Stoch', 'Thomas Morgenstern', 'Matti Nykänen', 'Jens Weissflog', 'Ryoyu Kobayashi'],
  datasets: [
    {
      label: 'Najwięcej razy na podium w konkursach PŚ',
      backgroundColor: '#eab308',
      data: [118, 108, 92, 88, 80, 80, 76, 76, 73, 66],
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
