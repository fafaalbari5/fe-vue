<script setup lang="ts">
import CardProduct from "@/components/CardProduct.vue";
import { onMounted, ref } from "vue";

const product = ref([]);
const fetchProducts = async () => {
  const response = await fetch(
    "https://6909c69b1a446bb9cc1ff256.mockapi.io/api/products/APIProduct"
  );
  product.value = await response.json();
  console.log("Berhasil fetch data");
};

onMounted(() => {
  fetchProducts();
});
</script>

<template>
  <div>
    <h1>Home Page</h1>
    <p>Ini adalah halaman Home</p>
  </div>

  <div class="flex flex-row flex-wrap justify-center">
    <div v-for="item in product" :key="item.id">
      <CardProduct :product="item" />
    </div>
  </div>
</template>
