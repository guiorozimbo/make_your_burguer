<template>
  <div id="nav">
   <router-link to="/" id="logo_url">
     <img :src="logo" :alt="alt" id="logo">
   </router-link>
   <router-link to="/">Home</router-link> 
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
 #nav{
   display: flex;
   justify-content: space-between;
   align-items: center;
   padding: 10px;
   background-color: #333;
   color: #fff;
 }
 #nav #logo_url{
   margin: auto;
   margin-left: 0;
 }
 #logo{
   width: 40px;
   height: 40px;
 }
 #nav a {
   color: #fcba03;
   text-decoration: none;
   margin: 12px;
   transition: .5s;
 }
 #nav a:hover{
   color: #FFF;
 }
 
 </style>