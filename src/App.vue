<template>
  <vHeader />
  <TodoList class="TodoList"
    v-bind:todos="todos"
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
        {"id":0,"title":"Go to codepen and get inspired","done":false},
        {"id":1,"title":"Pick a project","done":false},
        {"id":0,"title":"Go to codepen and get inspired","done":false},
        {"id":1,"title":"Pick a project","done":false},
        {"id":0,"title":"Go to codepen and get inspired","done":false},
        {"id":1,"title":"Pick a project","done":false},
        {"id":4,"title":"Create a new pen","done":true}
      ]
    }
  },
  mounted() {
    if (localStorage.todos) {
      this.todos = localStorage.todos
    }
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
