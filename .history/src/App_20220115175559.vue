<template>
  <smartphone>
    <v-app>


    <v-app-bar >
      <!-- -->
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>

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
