<script setup>
  
</script>
<template>
  <v-app>

    <v-navigation-drawer app>
      <BarraMenu />
    </v-navigation-drawer> 

    <v-main>
      <router-view />
    </v-main>
    
  </v-app>
</template>

<style>
  .v-main {
    background-color: #1D2939;
  }
</style>

