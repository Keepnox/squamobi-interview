<template>
    <v-card class="mb-5">
      <div class="d-flex ">
        <div>
          <v-card-title class="text-h5" v-text="title"></v-card-title>

          <v-card-text > {{desc}} </v-card-text>
          <v-card-actions>
          </v-card-actions>
        </div>

        <v-avatar
          class="ma-3"
          size="60"
          tile
        >
          <v-img :src="image"></v-img>
        </v-avatar>
      </div>
    </v-card>
</template>
<script>
export default {
  props: ["desc", "title", "image"],
  mounted() {
    console.log(this.items)
  }
}
</script>