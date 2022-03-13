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
    todo: []
    
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
    background-image: url(https://psv4.userapi.com/c240331/u137781259/docs/d17/665dd9ece954/5028066.png?extra=TOmqX89AWxhEMQi1zX4Jmxt2fd5lgzQYkw3DpdYB62tzoAS_GsoykEL_90IEbg0dKY8tX2bAXFS_32qXfFRCvWn_i6EFCQ-rXNHVlf-3GO8MfrCoDP4dw4ulbmSkb0px-2bWT-Tq2MsMUsj7BNbP9nG3);
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
