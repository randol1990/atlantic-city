<script setup>
  import { ref } from 'vue';

// Datos de la línea (pueden venir de tu API en Node.js)
const series = ref([{
  name: "Visitas",
  data: [10, 41, 35, 51, 49, 62, 69, 91, 148]
}]);

const chartOptions = ref({
  chart: {
    height: 350,
    type: 'line',
    zoom: { enabled: false },
    toolbar: { show: false },
    foreColor: '#FFFFFF' // Asegura que los textos sean blancos para tu tema oscuro
  },
  dataLabels: {
    enabled: false
  },
  stroke: {
    curve: 'smooth', // Hace que la línea sea curva en lugar de quebrada
    width: 3
  },
  colors: ['#00E396'], // Un color verde neón que resalta en fondos oscuros
  grid: {
    borderColor: '#40475D', // Color de las líneas de fondo para que no contrasten de más
  },
  xaxis: {
    categories: ['Ene', 'Feb', 'Mar', 'Abr', 'May', 'Jun', 'Jul', 'Ago', 'Sep'],
  },
  tooltip: {
    theme: 'dark' // Tooltip optimizado para modo oscuro
  }
});
</script>
<template>
  <v-card variant="outlined" class="mx-auto" max-width="600">
    <v-card-title class="d-flex align-center">
      <v-icon icon="mdi-chart-line" class="me-2" color="info"></v-icon>
      Tendencia de Visitas
    </v-card-title>
    
    <v-card-text>
      <apexchart
        type="line"
        height="200"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </v-card-text>
  </v-card>
</template>
<style></style>