<script setup>
  import { ref } from 'vue';

  // Datos de las columnas
  const series = ref([{
    name: 'Sesiones',
    data: [44, 55, 57, 56, 61, 58, 63]
  }]);

  // Configuración estética
  const chartOptions = ref({
    chart: {
      type: 'bar',
      toolbar: { show: false } // Oculta el menú de descarga para un look más limpio
    },
    plotOptions: {
      bar: {
        horizontal: false,
        columnWidth: '55%',
        borderRadius: 4, // Bordes redondeados como en los componentes de Vuetify
        dataLabels: {
          position: 'top', 
        },
      },
    },
    dataLabels: {
      enabled: false
    },
    stroke: {
      show: true,
      width: 2,
      colors: ['transparent']
    },
    xaxis: {
      categories: ['Lun', 'Mar', 'Mié', 'Jue', 'Vie', 'Sáb', 'Dom'],
    },
    yaxis: {
      title: { text: 'Cantidad' }
    },
    fill: {
      opacity: 1,
      colors: ['#1976D2'] // Color Primary de Vuetify
    },
    tooltip: {
      y: {
        formatter: (val) => `${val} visitas`
      }
    }
  });
</script>



<template>
  <v-card variant="outlined" class="mx-auto" max-width="600">
    <v-card-title class="d-flex align-center">
      <v-icon icon="mdi-bar-chart" class="me-2" color="primary"></v-icon>
      Rendimiento Semanal
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

<style>
    /* Hacer a los elementos del menú desplegable sean legibles */
    .apexcharts-menu {
        background: #2b2d3e !important; /* Un fondo oscuro para el cuadro */
        color: #ffffff !important;      /* Letras blancas */
        border: 1px solid #444 !important;
    }

    .apexcharts-menu-item:hover {
    background: #41B883 !important; /* Color de realce al pasar el mouse */
    }

    /* Cambia el fondo y el color de letra del cuadro flotante */
    .apexcharts-tooltip {
    background: #1e1e26 !important;
    color: #ffffff !important;
    border: 1px solid #444 !important;
    box-shadow: 2px 2px 10px rgba(0,0,0,0.5) !important;
    }

    /* Cambia el título dentro del tooltip (ej. el año o categoría) */
    .apexcharts-tooltip-title {
    background: #2b2d3e !important;
    border-bottom: 1px solid #444 !important;
    color: #41B883 !important; /* Color verde Vue */
    }

    .apexcharts-xaxis-label,
    .apexcharts-yaxis-label {
      fill: #ffffff !important; /* Letras blancas en los ejes */
    }
</style>