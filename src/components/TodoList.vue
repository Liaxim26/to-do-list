<template>
  <div>
    <AddTodo 
      @add-todo="addTodo"
    />
    <select v-model="filter">
      <option value='all'>Все</option>
      <option value='done'>Выполненные</option>
      <option value='not-done'>Не выполненные</option>
    </select>
    <ul>
      <TodoItem 
        v-for="todo in filteredTodods" :key="todo.id" todo_prop.sync="todo"
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
  data(){
    return{
      filter: 'all',
    }
  },
  computed: {
    filteredTodods() {
      var filter 
      if(this.filter === 'all') {
        return this.todos
      }
      if (this.filter === 'done') {
        return this.todos.filter(t => t.done)
      }
      if (this.filter === 'not-done'){
        return this.todos.filter(t => !t.done)
      }
      return filter
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
select{
    margin-top: 15px;
    padding: 6px 15px;
    border-radius: 5px;
    background: #e0e8f5;
    font-size: 17px;
    outline: none;
}
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
