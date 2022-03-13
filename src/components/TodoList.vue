<template>
  <div>
    <AddTodo />
    <ul>
      <TodoItem 
        v-for="(todo, id) in todos" :key="id"
        v-bind:todo = "todo"
      />
    </ul>
  </div>
</template>

<script>
import AddTodo from './AddTodo.vue'
import TodoItem from './TodoItem.vue'
export default {
  name: 'TodoList',
  props: {
    todos: {
      type: Object,
      required: true
    }
  },
  components: {
    AddTodo, TodoItem
  }
}
</script>

<style scoped>
ul{
  width: 400px;
  margin: 0 auto;
  list-style-type: none;
  padding-bottom: 50px;
}
</style>
