<template>
  <div class="pa-4 text-center">
    <v-dialog v-model="dialog" max-width="60%">
      <template v-slot:activator="{ props: activatorProps }">
        <v-btn
          class="text-none font-weight-regular"
          text="AGREGAR"
          variant="tonal"
          v-bind="activatorProps"
        ></v-btn>
      </template>

      <v-card prepend-icon="mdi-account" title="Registro de Usuarios">
        <v-card-text>
          <v-row dense>
            <v-col cols="12" md="6" sm="6">
            <v-text-field label="Nombres*" required> </v-text-field>
            </v-col>

            <v-col cols="12" md="6" sm="6">
            <v-text-field label="Apellido Paterno*" required></v-text-field>
            </v-col>
          </v-row>

          <v-row dense>
            <v-col cols="12" md="6" sm="6">
              <v-text-field label="Apellido Materno*" required></v-text-field>
            </v-col>

            <v-col cols="12" md="6" sm="6">
              <v-text-field label="Email*" required></v-text-field>
            </v-col>
          </v-row>

          <v-row dense>
            <v-col cols="12" sm="4">
              <v-select
                :items="['DNI', 'Carné de Extrangeria', 'Pasaporte']"
                label="Tipo de Documento*"
                required
              ></v-select>
            </v-col>

            <v-col cols="12" md="4">
              <v-text-field label="Numero de Documento*" required>
              </v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field label="Telefono*" required type="tel">
              </v-text-field>
            </v-col>
          </v-row>

          <v-row dense>
            <v-col cols="12" sm="6">
              <v-text-field
                label="Fecha de Nacimiento*"
                type="date"
                required
              ></v-text-field>
            </v-col>

            <v-col cols="12" sm="6">
              <v-select
                :items="['Administrador', 'Cajero', 'Recepcionista']"
                label="Rol*"
                required
              ></v-select>
            </v-col>
          </v-row>

          <v-row dense>
            <v-col cols="12" sm="6">
              <v-text-field label="Dirección*" required></v-text-field>
            </v-col>

            <v-col cols="12" sm="6">
              <v-select
                :items="['Peru', 'Venezuela', 'Ecuador', 'Bolivia', 'Argentina', 'Brasil', 'Colombia', 'Chile', 'Uruguay']"
                label="Lugar de Residencia*"
                required
              ></v-select>
            </v-col>
          </v-row>

          <v-row dense>
            <v-col cols="12" sm="6">
              <v-text-field
                label="Contraseña*"
                type="password"
                required
              ></v-text-field>
            </v-col>
  
            <v-col cols="12" sm="6">
              <v-text-field
                label="Confirmar Contraseña*"
                type="password"
                required
              ></v-text-field>
            </v-col>
          </v-row>

          <small class="text-caption text-medium-emphasis"
            >*Campos obligatorios</small
          >
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn text="Cerrar" variant="tonal" @click="dialog = false"></v-btn>

          <v-btn
            text="Guardar"
            variant="tonal"
            @click="dialog = false"
          ></v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>
<style>
  .v-btn {
    background-color: #17a2b8; /* Color de fondo azul */
    color: white; /* Color del texto blanco */
  }
</style>

<script setup>
  import { shallowRef } from 'vue'

  const dialog = shallowRef(false)
</script>
