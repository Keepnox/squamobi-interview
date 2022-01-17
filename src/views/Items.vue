<template>
  <div id="itemPage">
    <img class="header-image" :src="item.image"  alt="">
    <h3>{{item.title}}</h3>
    <p>{{item.description}}</p>
    <div class="back-button" @click="$router.go(-1)"> <img src="https://cdn-icons-png.flaticon.com/512/93/93634.png" alt=""> </div>
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
#itemPage .header-image {
  width: 100%;
  height: 170px;
  object-fit: cover;
}
.back-button {
  position: absolute;
  height: 24px;
  bottom: 0;
}
.back-button img {
  height: 100%;
  width: 100%;
}
</style>