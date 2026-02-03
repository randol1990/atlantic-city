<script setup>
  import { ref } from 'vue';

  // Los datos del gráfico (valores numéricos)
  const series = ref([44, 55, 13, 43, 22]);

  // Configuración del gráfico
  const chartOptions = ref({
    chart: {
      type: 'pie',
    },
    labels: ['Manzanas', 'Naranjas', 'Bananas', 'Uvas', 'Peras'],
    colors: ['#1976D2', '#fb8c00', '#4caf50', '#f44336', '#9c27b0'], // Colores estilo Vuetify
    legend: {
      position: 'bottom'
    },
    responsive: [{
      breakpoint: 480,
      options: {
        chart: {
          width: 200
        },
        legend: {
          position: 'bottom'
        }
      }
    }]
  });
</script>

<template>
  <v-card variant="outlined" class="mx-auto" max-width="300">
    <v-card-title class="text-center">Distribución de Ventas</v-card-title>
    
    <v-card-text>
      <apexchart
        type="pie"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </v-card-text>
  </v-card>
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
  color: #ffffff !important;
}
</style>
