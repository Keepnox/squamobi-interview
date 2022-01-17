<template>
  <div id="squamobi">
    <div class="quest" style="position: absolute;">
      <vue-markdown># **Squamobi Flutter Interview**

_This application is made with javascript as an example._

A ToDo list application will be made using Dart/Flutter. In practice, the features we want are as follows.

- You can design the interface as you like
- Add new ToDo item and remove selected ToDo item
- When adding ToDo list props
  - Title
  - Description
  - Image (In gallery)
- Changes made to the Todo list will not be lost when the application is closed and opened
- There will be an internal page for each todo
- On the inner pages, the title, description and image of the selected todo will appear.

## **Packages that we expect to be used**

|               | Packages                  |
| ------------- | ------------------------- |
| State Manager | Bloc, Getx, Provider etc. |
| Local DB      | Hive, Sqlite, Moor, etc.  |
| Permission    | Required to upload photos |

## Development

You need to forward the application by sharing it to the user of kimbukaan@gmail.com via github and sharing the apk with a file upload service. You can use internet application development.

_The application/codes you have developed will not be used anywhere._
</vue-markdown>
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
export default {
  name: 'App',

  components: {
    Smartphone,
  },


};
</script>

<style>
#squamobi .quest {
  position: absolute;
  width: 30%;
}
#squamobi .main-logo {
  filter: invert(1);
  margin: 0 auto;
  padding: 3px;
  height: 90%;
}
</style>