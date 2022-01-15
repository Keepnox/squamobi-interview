<template>
  <smartphone>
    <v-app>




    <!-- Sizes your content based upon application components -->
    <v-main>
       <v-app-bar >
      <!-- -->
    </v-app-bar>

      <!-- Provides the application the proper gutter -->
      <v-container fluid>

        <!-- If using vue-router -->
        <router-view></router-view>
      </v-container>
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
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
