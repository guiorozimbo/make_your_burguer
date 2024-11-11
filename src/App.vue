<template>
<Navbar :logo="logo_src" :alt="app_name"/>
<Footer/>
  <router-view/>
</template>
<script>
import Navbar from "./components/NavBar.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    Navbar,
    Footer,
  },
  data() {
    return {
      logo_src: "/img/logaster-2019-02-0146-t-flame-logo-6.jpg",
      app_name: "Make burguer",
    };
  }
}
</script>
<style>
*{
  font-family: Helvetica;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.main-container{
  margin: 50px;
  min-height: 250px;
}
h1{
  text-align: center;
  font-size: 30px;
  margin-bottom: 20px;
  color: #333;
}
</style>
