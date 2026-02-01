<script setup>
import { ref } from 'vue'

const series = ref([44, 33, 23])

const options = ref({
  chart: {
    type: 'donut'
  },
  labels: ['Ventas', 'Marketing', 'Soporte'],
  legend: {
    position: 'bottom'
  }
})
</script>

<template>
  <apexchart
    type="donut"
    height="300"
    :options="options"
    :series="series"
  />
</template>

<style>
/* Contenedor */
.donut-wrapper {
  max-width: 360px;
  margin: 0 auto;
}

/* Tooltip */
.apexcharts-tooltip {
  background: #0f172a !important;
  color: #fff;
  border-radius: 10px;
  box-shadow: 0 10px 25px rgba(0,0,0,0.2);
}

/* Texto central del donut */
.apexcharts-datalabel-label {
  fill: #64748b;
}

.apexcharts-datalabel-value {
  fill: #0f172a;
}

/* Leyenda */
.apexcharts-legend-text {
  font-size: 13px !important;
}
</style>
