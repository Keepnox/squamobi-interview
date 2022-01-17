<template>
  <smartphone>
    <v-app>
    <v-main>
        <v-app-bar >
          <h2>Squamobi</h2>
        </v-app-bar>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-main>
  </v-app>
  </smartphone>

</template>

<script>
import Smartphone from './components/Smartphone.vue';

export default {
  name: 'App',

  components: {
    Smartphone,
  },

  
};
</script>

<style scoped>

</style>