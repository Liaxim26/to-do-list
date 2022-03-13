<template>
  <h2>Добавьте запись</h2>
  <form @submit.prevent = "onSubmit">
    <input type="text" v-model = "title" placeholder="Введите что-нибудь!">
    <button type="submit">Добавить</button>
  </form>
</template>

<script>


export default {
  name: 'AddTodo',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    onSubmit() {
      if (this.title.trim()){
        const newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false
        }
        localStorage.setItem('todos', JSON.stringify(newTodo));
        //localStorage.setItem('todos',(localStorage.getItem('todos') || '') + JSON.stringify(newTodo))
        this.title = ''
      }
    }
  },
  components: {
    
  }
}
</script>

<style scoped>
  h2{
    font-weight: 400;
    text-align: center;
    padding: 20px;
  }
  form{
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 20px;
  }
  input{
    outline: none;
    padding: 10px 26px;
    font-size: 17px;
    transition-duration: 0.5s;
    border-radius: 3px;
    border: 0;
    background: #e0e8f5;;
  }
  input:focus{
    box-shadow: 0px 0px 20px 10px rgb(29 27 38);
  }
  button{
      background: #ffffff00;
      outline: none;
      border: 1px solid white;
      color: white;
      padding: 10px 20px;
      font-size: 17px;
      border-radius: 3px;
      font-weight: 200;
      transition-duration: 0.5s;
  }
  button:hover{
    background: #222226;
  }
  button:active{
    border: 1px solid black;
    transition-duration: 0.1s;
  }
</style>
