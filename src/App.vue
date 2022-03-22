<template>
  <vHeader />
  <TodoList class="TodoList"
    v-bind:todos="this.todos"
    @remove-todo='removeTodo'
  />
  <vFooter />
</template>

<script>
import vHeader from './components/vHeader.vue'
import vFooter from './components/vFooter.vue'
import TodoList from './components/TodoList.vue'


export default {
  name: 'App',
  data() {
    return {
      todos: [
       {id: 1, title: 'my first todo1', done: false},
       {id: 2, title: 'my first todo2', done: false},
       {id: 3, title: 'my first todo3', done: false},
       {id: 4, title: 'my first todo4', done: false}
      ]
    }
  }, 
  mounted() {
    //this.getTodos();
  },
  methods: {
    // get all todos when loading the page
    getTodos() {
      if (localStorage.getItem('todos')) {
        this.todos = JSON.parse(localStorage.getItem('todos'));
      }
    },
    removeTodo(id) {
      console.log(id)
      console.log(this.todo)
         this.todos = this.todos.filter(t => t.id !== id)
    },
  },
  components: {
    vHeader, vFooter, TodoList,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;400;700&display=swap');
#app {
  font-family: 'Montserrat', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
  
  
}
* {
  margin: 0;
  padding: 0;
  font-family: 'Montserrat', sans-serif;
}
html,
body {
  height: 100%;
  
}
#app {
  display: flex;
  flex-direction: column;
  height: 100%;
}
.TodoList {
  flex: 1 0 auto;
  background: #333336;
}
footer {
  flex: 0 0 auto;
}
</style>
