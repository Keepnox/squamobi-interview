<template>
    <v-card class="mb-5">
      <div class="d-flex  justify-space-between">
        <div>
          <v-card-title class="text-h5" v-text="title"></v-card-title>
          <v-card-text > {{desc}} </v-card-text>
          <v-card-actions>
          </v-card-actions>
        </div>

        <v-avatar class="ma-3" size="60">
          <v-img :src="image"></v-img>
        </v-avatar>
        <img class="remove-icon" @click="removeItem(title)" src="https://www.pngrepo.com/png/66604/512/trash.png" alt="">
      </div>
    </v-card>
</template>



<script>
export default {
  props: ["desc", "title", "image"],
  mounted() {
    console.log(this.items)
  },
  methods: {
    removeItem(item) {
      let allData = JSON.parse(localStorage.getItem('todo'))
      var filteredData = allData.filter(i => i.title != item);
      localStorage.setItem('todo', JSON.stringify(filteredData))
    }
  }
}
</script>



<style scoped>

  .remove-icon {
    position: absolute;
    width: 16px;
    object-fit: cover;
    right: 15px;
    bottom: 15px;
    cursor: pointer;
}
</style>