<template>
  <div id="itemPage">
    <img src="" alt="">
    <img :src="item.image"  alt="">
    <h3>{{item.title}}</h3>
    <p>{{item.description}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      item: {}
    }
  },
  mounted() {
    let data = JSON.parse(localStorage.getItem('todo'))
    console.log(data)
    this.item = data.find(d => d.id === this.$route.params.id)
  }
}
</script>

<style scoped>
#itemPage {
position: relative;
  height: 100%;
  width: 100%;
}
#itemPage img {
  width: 100%;
  height: 170px;
  object-fit: cover;
}
</style>