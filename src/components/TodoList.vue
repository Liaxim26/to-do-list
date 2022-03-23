<template>
  <div>
    <AddTodo 
      @add-todo="addTodo"
    />
    <ul>
      <TodoItem 
        v-for="todo in todos" :key="todo.id" todo_prop.sync="todo"
        v-bind:todo_prop = "todo"
        @remove-todo="removeTodo" 
        @done-todo="doneTodo"
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
      type: [Object, Array],
      required: true
    }
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id)
    },
    addTodo(todo) {
      this.$emit('add-todo', todo)
    },
    doneTodo(id){
      this.$emit('done-todo', id)
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

@media (max-width: 768px){
ul{
  width: 80%;
}
}
</style>
