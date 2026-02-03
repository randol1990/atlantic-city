<script setup>
  import { ref } from 'vue';

const series = ref([{
  name: 'Unidades Vendidas',
  data: [400, 430, 448, 470, 540]
}]);

const chartOptions = ref({
  chart: {
    type: 'bar',
    toolbar: { show: false }
  },
  plotOptions: {
    bar: {
      borderRadius: 4,
      horizontal: true, // Esta es la clave para que sea de barras y no de columnas
      barHeight: '70%',
      dataLabels: {
        position: 'end'
      },
    }
  },
  colors: ['#00897B'], // Un tono verde azulado tipo "Teal" de Vuetify
  dataLabels: {
    enabled: true,
    formatter: function (val) {
      return val + " uds";
    },
    offsetX: -6,
    style: {
      fontSize: '12px',
      colors: ['#fff']
    }
  },
  xaxis: {
    categories: ['Laptop Pro', 'Monitor 4K', 'Teclado Mecánico', 'Mouse Gamer', 'Webcam HD'],
  },
  grid: {
    xaxis: {
      lines: { show: true }
    }
  }
});
</script>

<template>
  <v-card variant="outlined" class="mx-auto" max-width="600">
    <v-card-title class="d-flex align-center">
      <v-icon icon="mdi-chart-bar-stacked" class="me-2" color="secondary"></v-icon>
      Ranking de Productos
    </v-card-title>
    
    <v-card-text>
      <apexchart
        type="bar"
        height="208"
        :options="chartOptions"
        :series="series"
      ></apexchart>
    </v-card-text>
  </v-card>
</template>

<style></style>