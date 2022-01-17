<template>
  <div id="listOuter">
    <TodoItem
      v-for="(t, index) in todoData"
      :key="index"
      :title="t.title"
      :desc="t.description"
      :image="t.image"
    ></TodoItem>

    <v-btn
          class="add-button"
          color="primary"
          elevation="3"
          fab
          v-on:click="dialog = !dialog"
        ><span style="font-size:34px;">+</span></v-btn>
        <div class="popup" v-if="dialog">
          <div>Add Todo</div>
          <input type="text" >
          <input type="text" >
        </div>
  </div>
</template>

<script>
// @ is an alias to /src

import TodoItem from '@/components/TodoItem.vue'

export default {
  name: 'Home',
  components: {TodoItem},
  data () {
    return {
      todoData: [],
      dialog: true,
    }
  },
  mounted () {
    this.todoData = JSON.parse(localStorage.getItem('todo'))
    console.log('selam')
  },
  created() {
    let defaultData = JSON.parse(localStorage.getItem('todo')) || [
        {
          title: "First Item",
          description: 'First Item Todo...',
          image: "https://unsplash.it/640/425?random"
        },
        {
          title: "Todo Item 2",
          description: 'Todo item 3.... lorem ipsum',
          image: "https://unsplash.it/640/425?random"
        },
        {
          title: "Todo Item 3",
          description: 'description todo 3 item..',
          image: "https://unsplash.it/640/425?random"
        },
      ]
    localStorage.setItem('todo', JSON.stringify(defaultData))
  }
}
</script>

<style >
.v-application--wrap {
  height: 100%;
  min-height: 100%;
}
.list-outer {
  position: relative;
  height: 100%;
  width: 100%;
}
.add-button {
  position: absolute;
  right: 10px;
  bottom: 10px;
}
.popup {
  position: absolute;
  height: 150px;
  width: 90%;
  top: 50%;
  transform: translateY(-50%);
  background-color: black;
}
</style>