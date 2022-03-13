<template>
    <li v-bind:class='{done: todo.done}'>
      <input type="checkbox">
      <span>{{todo.title}}</span>
      <span class='delete' v-on:click="$emit('remove-todo', todo.id)"></span>
    </li>
</template>

<script>


export default {
  name: 'TodoItem',
  props: {
    todo: {
      type: Object,
      required: true
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
    background-image: url(https://cdn-icons.flaticon.com/png/512/5028/premium/5028066.png?token=exp=1647171718~hmac=652e0f213e8e114cda26ff0ba020f3ce);
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
</style>
