<template>
<footer>
  <footerfr></footerfr>
</footer>
</template>

<script>
import footerfr from './components/footerfr.vue'
import * as Vue from 'vue'
import axios from 'axios'
import { VueAxios } from 'vue-axios';

export default {
  components: {
    footerfr

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
