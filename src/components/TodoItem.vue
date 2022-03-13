<template>
    <li>
      {{todo.title}}
    </li>
</template>

<script>


export default {
  name: 'TodoItem',
  props: {
    todo: {
    }
  },
  components: {
   
  }
}
</script>

<style scoped>
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
