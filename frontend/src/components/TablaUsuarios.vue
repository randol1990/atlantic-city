<script setup>
import { ref } from 'vue'

// Conexión del buscador a la tabla
const search = ref('')

// Definición de las columnas (Headers)
const headers = [
  { title: '#', key: 'id', align: 'start', sortable: true },
  { title: 'Nombres', key: 'nombres' },
  { title: 'Apellidos', key: 'apellidos' },
  { title: 'Email', key: 'email' },
  { title: 'Rol', key: 'rol' },
  { title: 'Estado', key: 'estado' },
  { title: 'Acciones', key: 'acciones', sortable: false }, // Columna para los botones
]

// Datos de prueba (Items)
const clientes = ref([
  { id: 1, nombres: 'Mark', apellidos: 'Otto', email: '@mdo', rol: 'Administrador', estado: 'Activo'},
  { id: 2, nombres: 'Jacob', apellidos: 'Thornton', email: '@fat', rol: 'Cajero', estado: 'Inactivo' },
  { id: 3, nombres: 'Larry', apellidos: 'the Bird', email: '@twitter', rol: 'Recepcionista', estado: 'Activo' },
  { id: 4, nombres: 'John', apellidos: 'Doe', email: '@jdoe', rol: 'Recepcionista', estado: 'Inactivo' },
  { id: 5, nombres: 'Jane', apellidos: 'Smith', email: '@jsmith', rol: 'Cajero', estado: 'Activo' },
])

// Funciones para los botones
const verCliente = (item) => console.log('Ver:', item)
const editarCliente = (item) => console.log('Editar:', item)
const borrarCliente = (item) => console.log('Borrar:', item)
</script>

<template>

    <!-- Contenedor de la tabla de clientes -->
    <v-card class="mt-5" variant="flat" color="transparent">
        <v-layout
        class="d-flex justify-space-between align-center mb-5">

            <!-- Campo de búsqueda -->
            <v-text-field
                v-model="search"
                :loading="loading"
                label="Buscar usuario"
                append-inner-icon="mdi-magnify"
                density="compact"
                variant="solo-filled"
                flat
                hide-details
                single-line
                @click:append-inner="onClick"
                max-width="30rem"
            ></v-text-field>

            <!-- Botón para agregar nuevo cliente -->
            <BotonAgregarUsuario />

        </v-layout>

        <!-- Tabla de datos -->
        <v-data-table
        :headers="headers"
        :items="clientes"
        :search="search"
        class="elevation-1 custom-table"
        density="comfortable"
        >
        <!-- Columna de acciones -->
        <template v-slot:item.acciones="{ item }">
            <div class="d-flex ga-3">
            <v-btn color="success" size="small" @click="verCliente(item)">Ver</v-btn>
            <v-btn color="warning" size="small" @click="editarCliente(item)">Editar</v-btn>
            <v-btn color="error" size="small" @click="borrarCliente(item)">Borrar</v-btn>
            </div>
        </template>
        </v-data-table>
    </v-card>
</template>

<style scoped>
    /* Estilo para que la tabla combine con tu fondo oscuro de Atlantic City */
    :deep(.custom-table) {
    background-color: #dedede !important;
    color: #1D2939 !important;
    border-radius: 8px;
    }

    :deep(.custom-table th) {
    font-weight: bold !important;
    color: #1D2939 !important;
    background-color: #f8f9fa !important; 
    }


    /* Estilos para el contenedor del campo de texto  del buscador*/
    :deep(.v-field) {
    background-color: white !important;
    color: black !important;
    opacity: 1 !important;
    margin: 1rem 0 !important;
    }

    
    :deep(.v-field__input) {
    color: black !important;
    }

  
    :deep(.v-field-label) {
    color: black !important;
    opacity: 0.7; 
    }

   
    :deep(.v-field__append-inner .v-icon) {
    color: black !important;
    }

    /* Estilos para el boton AGREGAR */
    .v-btn {
        background-color: #17A2B8; /* Color de fondo azul */
        color: white; /* Color del texto blanco */
    }
</style>