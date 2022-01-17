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
        <v-card class="popup" v-if="dialog">
          <div>Add Todo</div>
          <v-text-field
            label="Title"
            hide-details="auto"
          ></v-text-field>
          <v-text-field
            label="Description"
            hide-details="auto"
          ></v-text-field>
          <v-btn class="add">
            Add
          </v-btn>
        </v-card>
  </div>
</template>

<script>

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
  watch: {
    dialog(val) {
      console.log(val)
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
        }
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
  padding: 15px;
  /* height: 150px; */
  width: 90%;
  top: 50%;
  transform: translateY(-50%);
}
.popup .add {
  margin-top: 15px;
  float: right;
}
</style>