<script setup>
  import GraficoCircular from '@/components/GraficoCircular.vue'
</script>

<template>
  <v-layout>
    <v-app>
      <v-main>
        <v-row class="title" >
          <h2>Dashboard</h2>
        </v-row>

        <v-row justify="center">
          <v-col cols="12" md="4">
            <GraficoCircular />
          </v-col>

          <v-col cols="12" md="4">
            <GraficoColumna />
          </v-col>

          <v-col cols="12" md="4">
            <GraficoBarra />
          </v-col>
        </v-row>

        <v-row justify="center">
          <v-col cols="12" md="4">
            <GraficoLinea />
          </v-col>

          <v-col cols="12" md="4">
            <GraficoArea />
          </v-col>

          <v-col cols="12" md="4">
            <GraficoDonut />
          </v-col>
        </v-row>
        
      </v-main>


    </v-app>

  </v-layout>
  
  
  
</template>

<style>
  .title{
    margin: 1rem;
  }
</style>

