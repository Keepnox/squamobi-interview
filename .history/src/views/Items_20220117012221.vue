<template>
  <div>
    <img :src="item.image" style="width: 100%;" alt="">
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