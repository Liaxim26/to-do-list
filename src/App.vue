<template>
  <vHeader />
  <TodoList class="TodoList"
    v-bind:todos="this.todos"
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
      todos: []
    }
  }, 
  mounted() {
    this.getTodos();
  },
  methods: {
    // get all todos when loading the page
    getTodos() {
      if (localStorage.getItem('todos')) {
        this.todos = JSON.parse(localStorage.getItem('todos'));
      }
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
