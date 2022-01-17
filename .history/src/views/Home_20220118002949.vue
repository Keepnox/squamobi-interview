<template>
  <div id="listOuter">
    <TodoItem
      :to="esea"
      v-for="(t, index) in todoData"
      :key="index"
      :title="t.title"
      :id="t.id"
      :desc="t.description"
      :image="t.image"
      v-on:removeClick="removeItem(t.id)"
    ></TodoItem>

    <v-btn
          class="add-button"
          color="primary"
          elevation="3"
          fab
          v-on:click="dialog = !dialog"
        ><span style="font-size:34px;">+</span></v-btn>
        <v-card class="popup" v-if="dialog">
          <div class="popup-title">Add Todo</div>
          <v-text-field
            label="Title"
            hide-details="auto"
            v-model="title"
          ></v-text-field>
          <v-text-field
            label="Description"
            hide-details="auto"
            v-model="description"
          ></v-text-field>
          <v-text-field
            label="Image Url"
            hide-details="auto"
            v-model="image"
          ></v-text-field>
          <v-btn class="add" v-on:click="addTodo">
            Add
          </v-btn>
        </v-card>
  </div>
</template>

<script>

import TodoItem from '@/components/TodoItem.vue'
import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'Home',
  components: {TodoItem},
  data () {
    return {
      todoData: [],
      dialog: false,
      image: "",
      description: "",
      title: ""
    }
  },
  watch: {
    dialog(val) {
      if(val) {
        document.getElementsByTagName('body')[0].classList.add('popup-active')
      } else {
        document.getElementsByTagName('body')[0].classList.remove('popup-active')
      }
    }
  },
  mounted () {
    this.todoData = JSON.parse(localStorage.getItem('todo'))
  },
  created() {
    let defaultData = JSON.parse(localStorage.getItem('todo')) || [
        {
          title: "First Item",
          description: 'First Item Todo...',
          image: "https://unsplash.it/640/425?random",
          id: uuidv4()
        },
      ]
    localStorage.setItem('todo', JSON.stringify(defaultData))
  },
  methods: {
    removeItem(item) {
      console.log(item)
      let allData = this.todoData
      var filteredData = allData.filter(i => i.id != item);
      localStorage.setItem('todo', JSON.stringify(filteredData))
      this.todoData = filteredData
    },
    addTodo() {
      this.todoData.push(
        {
          title: this.title,
          description: this.description,
          image: this.image,
          id: uuidv4()
        }
      );
      localStorage.setItem('todo', JSON.stringify(this.todoData));
      this.dialog = false;
    }
  }
}
</script>

<style >
.v-application--wrap {
  height: 100%;
  min-height: 100%;
  overflow: hidden;
  overflow-y: scroll;
}

.v-application--wrap:before {
  content: "";
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.4);
  z-index: 1;
}

.v-main, v-main__wrap {
  height: 100%;
}
.v-main .container {
  height: calc(100% - 55px);
}
.list-outer
.list-outer {
  position: relative;
  height: 100%;
  width: 100%;
}
.add-button {
  position: fixed;
  right: 50%;
  transform: translatex(220%);
  top: 50%;
}
.popup {
  position: absolute;
  padding: 15px;
  width: 90%;
  top: 50%;
  transform: translateY(-50%);
}
.popup .add {
  margin-top: 20px;
  float: right;
}
.popup .popup-title {
  font-weight: 900;
}
</style>