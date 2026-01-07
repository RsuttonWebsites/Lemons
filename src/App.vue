<template>
  <v-app>
    <v-app-bar color="primary" class="">
      <v-app-bar-title>Lemons</v-app-bar-title>
      
      <v-spacer></v-spacer>
      
      <v-btn to="/" class="mx-1">Home</v-btn>
      <v-btn to="/life" class="mx-1">Life</v-btn>
      <v-btn to="/measurements" class="mx-1">Measurements</v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script setup>
  //
</script>
