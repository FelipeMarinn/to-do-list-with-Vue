<template>
  <li>
    <input class="todo-checkbox" 
           v-bind:id="'item_' + item.id" 
           v-model="item.done" type="checkbox">
    <label v-bind:for="'item_' + item.id"></label>
    <span class="todo-text">{{ item.title }}</span>
    <span class="delete" v-on:click.prevent="deleteItem(item)"></span>
</li>
</template>

<script>
export default {
  name: 'Tarea',
  props: {
    todoList:Array,
    item: Object
  },
  methods: {
    deleteItem:function(item) {
      this.todoList.splice(this.todoList.indexOf(item), 1);
    }
  }
}
</script>
