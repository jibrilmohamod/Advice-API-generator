<template>
 <div id="app">
  <advice></advice>
  <footer>
   <footerfr> </footerfr>
  </footer>
 </div>
</template>

<script>
 import footerfr from "./components/footerfr.vue"
 import advice from "./components/advice.vue"

 export default {
  components: {
   footerfr,
   advice,
  },
 }
</script>

<style>
 * {
  box-sizing: border-box;
  /* height: 100%; */
  background-color: hsl(218, 23%, 16%);
  font-family: "Manrope", sans-serif;
 }
 #app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  width: 100;
 }
</style>
