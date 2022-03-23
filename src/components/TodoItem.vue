<template>
    <li v-bind:class='{done: todo.done}'>
      <!-- <input type="checkbox" @change="todo.done = !todo.done"> -->
      <input type="checkbox" v-model='check' @change="$emit('done-todo', todo.id)">
      <span>{{todo.title}}</span>
      <span class='delete' @click="$emit('remove-todo', todo.id)"></span>
    </li>
</template>

<script>


export default {
  name: 'TodoItem',
  props: {
    todo_prop: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      todo: this.todo_prop,
      check: false
    }
  },
  mounted() {
    this.checked()
  },
  methods: {
    checked() {
      if(this.todo.done == 1){
        this.check = true
      }
    }
  },
  components: {
   
  }
}
</script>

<style scoped>
.delete{
    position: absolute;
    height: 100%;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
    cursor: pointer;
    opacity: 0;
    width: 0;
    background-color: #FF3F5B;
    color: #fff;
    transition: all ease-in 0.25s;
}
li:hover .delete {
    width: 60px;
    opacity: 1;
}
.done{
  text-decoration: line-through;
}
li .delete:after {
    position: absolute;
    content: '';
    width: 16px;
    height: 16px;
    top: 50%;
    left: 50%;
    background-image: url(/src/assets/del-btn.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    transform: translate(-50%, -50%) scale(2.5);
    transition: all ease-in 0.5s;
}
input{
  position: absolute;
  cursor: pointer;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  width: 22px;
  height: 22px;
  border-radius: 2px;
  border: 1px solid #cfdcec;
  background-color: #fff;
}
li{
  position: relative;
  list-style-type: none;
  display: block;
  margin: 10px 0;
  background: #e0e8f5;
  border-radius: 3px;
  padding-left: 38px;
  padding-top: 12px;
  padding-bottom: 12px;
  padding-right: 49px;
  overflow: hidden;
  color: black;
}

@media (max-width: 768px){
.delete {
    opacity: 1;
    width: 60px;
}
}
</style>
