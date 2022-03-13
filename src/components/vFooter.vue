<template>
  <footer>
    <p>
      какой-то <br>
      <span>footer</span><br> 
      для <br> 
      тестового задания <br> 
      выполненного <br> 
      <span>Соляным Михаилом</span> <br> 
      © 2022
    </p>
    
  </footer>
</template>

<script>


export default {
  name: 'vFooter',
  components: {
    
  }
}
</script>

<style scoped>
footer{
  background: #222226;
  margin: 0;
  padding: 0; 
  width: 100%;
  font-size: 17px;
  line-height: 150%;
  font-weight: 200;
  padding : 20px 0;
  text-align: center;
}
span{
  text-transform: uppercase;
  font-size: 20px;
}

@media (max-width: 768px){
  footer{
    font-size: 14px;
  }
  span{
    text-transform: uppercase;
    font-size: 17px;
  }
}
</style>
