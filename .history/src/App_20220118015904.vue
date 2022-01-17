<template>
  <div id="squamobi">
    <div class="quest" style="position: absolute;">
      For instructions you can  <a href="https://github.com/Keepnox/squamobi-interview#readme">read here</a>
    </div>
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
// import mdQuest from './assets/quest.md'
export default {
  name: 'App',

  components: {
    Smartphone,
  },
  data: () => ({
    // mdQuest
  })

};
</script>

<style>
#squamobi .quest {
  position: absolute;
  /* width: 30%; */
}
#squamobi .main-logo {
  filter: invert(1);
  margin: 0 auto;
  padding: 3px;
  height: 90%;
}
</style>