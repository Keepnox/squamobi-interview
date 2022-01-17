<template>
  <smartphone>
    <v-app>
    <v-main>
        <v-app-bar >
        <img src="https://cdn-icons-png.flaticon.com/512/93/93634.png" alt="">

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

  data: () => ({
    //
  }),
};
</script>
