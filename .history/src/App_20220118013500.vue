<template>
  <div id="squamobi">
    <div class="quest" style="position: absolute;"></div>
    <smartphone>
      <v-app>
      <v-main>
          <v-app-bar >
            <img class="main-logo" src="https://squamobi.com/wp-content/uploads/2021/11/sdffsdfds.png" alt="">
          </v-app-bar>
        <v-container fluid>
          <router-view></router-view>
        </v-container>
      </v-main>
    </v-app>
    </smartphone>
  </div>
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
.main-logo {
  filter: invert(1);
  margin: 0 auto;
  height: 90%;
}
</style>