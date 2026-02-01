
<script setup>
import { ref } from 'vue';
// Importamos el componente
import VueApexCharts from "vue3-apexcharts";

// Registramos el componente localmente
const apexchart = VueApexCharts;

// Definimos los datos reactivos con ref()
const series = ref([{
    name: 'Ventas',
    data: [30, 40, 35, 50, 49, 60, 70, 91]
}]);

const chartOptions = ref({
  chart: {
    id: 'vuechart-example',
    theme: {
      mode: 'dark' // Modo oscuro
    }
  },
  xaxis: {
      categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998]
  },
  colors: ['#41B883'] // Verde característico de Vue
});
</script>



<template>
  <div id="chart">
    <!-- "options" determina el diseño y el comportamiento del gráfico -->
    <!-- "series" determina los datos que se muestran en el gráfico-->
    <apexchart
      width="100%"
      type="bar"
      :options="chartOptions"
      :series="series" 
    ></apexchart>
  </div>
  
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