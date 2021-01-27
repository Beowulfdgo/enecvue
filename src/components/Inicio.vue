<template>
  <div class="Home">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import axios from 'axios'
//import VueAxios from 'vue-axios'
export default {
  name: "Inicio",

  data: function () {
    return {
      cuestionario: "",
    };
  },

  props: {
    msg: String,
  },
  mounted() {
    var self = this;
    //../assets/logo.png
   // self.axios.get("/assets/json/enunciado1.json").then((response) => {
       axios.get("https://api.coindesk.com/v1/bpi/currentprice.json").then((response) => {
      
      self.cuestionario = response.data;
    });
  },
};
</script>

<style></style>
