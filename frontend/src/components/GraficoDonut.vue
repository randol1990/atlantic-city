<template>
  <v-card variant="outlined" class="mx-auto" max-width="290">
    <v-card-title class="text-center">Segmentación de Clientes</v-card-title>
    
    <v-card-text>
      <apexchart
        type="donut"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </v-card-text>
  </v-card>
</template>

<script setup>
import { ref } from 'vue';

// Datos para la segmentación (ejemplo: Plata, Oro, Platino)
const series = ref([45, 30, 25]);

const chartOptions = ref({
  chart: {
    type: 'donut',
    foreColor: '#FFFFFF'
  },
  labels: ['Nuevos', 'Recurrentes', 'VIP'],
  colors: ['#1E88E5', '#FFB300', '#E53935'], // Colores distintivos
  plotOptions: {
    pie: {
      donut: {
        size: '70%', // Grosor de la dona
        labels: {
          show: true,
          total: {
            show: true,
            label: 'Total',
            color: '#FFFFFF',
            formatter: (w) => {
              return w.globals.seriesTotals.reduce((a, b) => a + b, 0)
            }
          }
        }
      }
    }
  },
  legend: {
    position: 'bottom'
  },
  tooltip: {
    theme: 'dark'
  }
});
</script>