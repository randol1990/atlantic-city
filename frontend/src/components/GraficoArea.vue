<script setup>
import { ref } from 'vue';

const series = ref([{
  name: 'Ingresos S/.',
  data: [31, 40, 28, 51, 42, 109, 100]
}]);

const chartOptions = ref({
  chart: {
    type: 'area',
    height: 350,
    toolbar: { show: false },
    foreColor: '#FFFFFF'
  },
  dataLabels: {
    enabled: false
  },
  stroke: {
    curve: 'smooth',
    width: 2
  },
  fill: {
    type: 'gradient',
    gradient: {
      shadeIntensity: 1,
      opacityFrom: 0.7,
      opacityTo: 0.2,
      stops: [0, 90, 100]
    }
  },
  colors: ['#FB8C00'], // Color naranja de Vuetify
  xaxis: {
    categories: ['Lun', 'Mar', 'Mié', 'Jue', 'Vie', 'Sáb', 'Dom'],
  },
  tooltip: {
    theme: 'dark'
  }
});
</script>

<template>
  <v-card variant="outlined" class="mx-auto" max-width="600">
    <v-card-title class="d-flex align-center">
      <v-icon icon="mdi-chart-areaspline" class="me-2" color="warning"></v-icon>
      Ingresos por Promociones
    </v-card-title>
    
    <v-card-text>
      <apexchart
        type="area"
        height="200"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </v-card-text>
  </v-card>
</template>

<style></style>

