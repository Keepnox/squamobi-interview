<template>
  <p>
    selam
  </p>
</template>

<script>
export default {
  mounted() {
    let data = JSON.parse(localStorage.getItem('todo'))
    console.log(data)
    console.log(this)
  }
}
</script>