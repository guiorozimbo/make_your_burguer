<template>
  <div id="main-banner">
    <h1>Make your burger</h1>
  </div>
</template>

<script>
export default{
name: "Banner"
}
</script>

<style scoped>
#main-banner{
background-image: url('/public/img/nossas-reservas.jpg');
background-position: 0 -250px;
background-size: cover;
height: 500px;
display: flex;
align-items: center;
justify-content: flex-start;
}
#main-banner h1{
  color: white;
  text-align: center;
  font-size: 60px;
  font-weight: 700;
  padding-left: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}
</style>