<template>
  <div>
    <AddTodo />
    <TodoItem 
      v-for="(todo, id) in todos" :key="id"
      v-bind:todo = "todo"
    />
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

</style>
