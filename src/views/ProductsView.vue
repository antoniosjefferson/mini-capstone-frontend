<script>
import axios from "axios";

export default {
  data: function () {
    return {
      products: [],
    };
  },
  created: function () {
    axios.get("/all_products.json").then((response) => {
      this.products = response.data;
    });
  },
  methods: {},
};
</script>

<template>
  <h1>THIS SHOULD WORK</h1>
  <div class="all_products">
    <div v-for="product in products" v-bind:key="product.name">
      <h1>{{ product.name }}</h1>
    </div>
  </div>
</template>

<style></style>
