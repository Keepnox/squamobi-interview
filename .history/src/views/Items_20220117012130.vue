<template>
  <img :src="item.image"  alt="">
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