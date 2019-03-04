<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <img src="red-banana-benefits_620x350_41498045864.jpg" alt="">
    <div v-for="product in products">
      <p>Id: {{ product.id }}</p>
      <p>Name: {{product.name }}</p>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      products: []
    };
  },
  created: function() {
    axios.get("/api/products").then(response => {
      this.products = response.data;
    });
  },
  methods: {}
};
</script>
