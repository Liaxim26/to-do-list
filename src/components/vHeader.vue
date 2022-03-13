<template>
  <header>
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAkFBMVEUdGyb///8AAAAaGCP39vcfHSkYFiIGABbn5ucVEyCNjJAMCBkAAAQxLzjIyMkTEB59fIAAAAsAABOHhorAv8EAAA/U1NXg4OH4+PgAABSlpadqaW5bWmBPTlTt7e1GRUwnJS+1tbd2dXk4Nj63triZmZtvbnJgX2SXl5rGxsg+PURVVFqsq66hoaQrKTPj4uS7F6LgAAAD+0lEQVR4nO3ZaXOqPACGYQgUtLghKGjdW083bf//v3srSkUgy5wB3zkz9/VRY8hjFkKwLAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAOAf4wz9SRiGk6DbQGVecKornA2dBiqrv4JQG5d/EIjZ4vEQxy+HaCl6w/LXzs2ve5NA1fJuKJ5H85c43u6fHOG3EtLr265KGoc35X2xG9i/0nghbjM6D3aa/zR1k8H8TyACWT7xcVhdK0se/Uk7CdUGvWJpMXJL3ycLUfzrfxKWTUf1GcPnQbnoUVTGxH0T+v2kpkQcFuZjTULbdkfCq1xYHOtKfvbKBe+ZMHyqL7LqX//52oQ//bgpdaPnT+srexT/X8Lwj6xMeo0oSWjbS/82YEdW2b7hiOYJg4W8kDvMR6E0ob0uTjFRN9wvotBqknFCz1KVmuZ/vDxh2r3ORfGiqmzd6HJjnFBI5s1FNNMlvP4L1vBVWdeq0XFqmlDTKNseO7qE9lPeN2IlL3QS+ZLWtplQNXEyb2NtwuTSN8FOU5fbZCcaJuyuNcXyoaVKaK/PN07NgLcLvX2/hJODrlH2sqtNOM92Zd5GW1fc4HJqmFB8a1v1NtMmPA/TINLW1eRao004PSV0fG2j7PeeNqGdNTzc6it7aPAxYxONTnbly6522eej19OU8D70jTp3kDrh5nRL1E9D2140eUsMMuKxdI2OOH+RXUp7r7DzkaVOmM1VId2wXe1kT1x/z68mLHw7lOy5i1KDhJ9Dw4Sjuyc06EP3n+5D/e0w/4E6Yd90Hr42/ySsTug4+kYNDBKe19JYX9lX5Ym55YTaneSP41ib8LzcVi5V1ei2zSxhqHzcyZwXeGXCQ7anMRjy742fZWgT6pca12BfernL6QdECwuNLqG+VceJNmFe5exNU1fawiDVJvR1m0lP/3yY3+ScmaaufeUY+g4JdZ24vxzmKhImvzWO1WtNG+uMQcLhUtWo39KKhP3rsar6ebrRTal5Qqunmj1f+rO218LRhPIRsenjROOElthKG7X8XfukCZ9uHmoD+R1j205Ak4SWmNe3KV1fu0eScLUuLR7+Oq2v7NBSQKOElqg9QkoeCnev+oTz6huXwKqdi7u2ApoltHyrsqd0o5u3LjUJ3bkT1jyyeyKqdGNsNXmOWGq7UcKfZn1si+1KInHbplLC1WC/FBPJNtoXUfH4J90+V19RNcjp3vIkJyXdUCyO70mn8z3dRl+i8p87z7/6G1+IsepVuC/60cv0u9NJ4v2nCNvMd2paibzkcNzLXmGHQV2TvCtVJXnpIDzXNW7lJggAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD8nf8AuQo5iCJUvtUAAAAASUVORK5CYII=">
    <h1>Какой-то HEADER</h1>
  </header>
</template>

<script>


export default {
  name: 'vHeader',
  components: {
    
  }
}
</script>

<style scoped>
header{
  text-align: center;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 2%;
  justify-content: center;
  background: #1d1b26;
  padding: 10px;
  box-shadow: 0px 5px 10px 0px rgb(29 27 38);
}
img{
  width: 100px;
  height: auto;
  border: 3px solid white;
}
h1{
  font-weight: 400;
}

@media (max-width: 768px){
  header{
    flex-direction: column;
  }
  img{
    width: 80px;
  }
  h1{
    font-size: 24px;
    padding-top: 10px;
  }
}
</style>
