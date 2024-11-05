<template>
<Navbar :logo="logo_src" :alt="app_name"/>
<Footer/>
  <router-view/>
</template>
<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    Navbar,
    Footer,
  },
}
</script>
<style>

</style>
