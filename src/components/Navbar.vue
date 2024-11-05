<template>
 <div id="nav">
  <router-link to="/">
    <img :src="logo" :alt="alt" id="logo">
  </router-link>
  <router-link to="/">Home</router-link> |
  <router-link to="/pedidos">Pedidos</router-link>
 </div> 
</template>

<script>
export default{
  name: "Navbar",
  props:["logo", "alt"]
 /* data() {
    return {
      selected: null,
      options: [
        { value: 1, text: 'Option 1' },
        { value: 2, text: 'Option 2' },
        { value: 3, text: 'Option 3' },
        { value: 4, text: 'Option 4' },
        { value: 5, text: 'Option 5' },
      ],
    }
  },
  methods: {
    handleSelect(selected) {
      this.selected = selected;
    },
  },*/
}
</script>
<style scoped>
/* CSS styles */
.custom-select {
  width: 200px;
  border: 1px solid #ccc;
  padding: 5px;
  border-radius: 5px;
  background-color: #fff;
}

</style>