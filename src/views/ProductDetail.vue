<script setup>
import { useRouter } from "vue-router";
import CardProduct from "@/components/CardProduct.vue";
import { onMounted, ref } from "vue";

const router = useRouter();
const id = router.currentRoute.value.params.id;

const product = ref([]);
const fetchProducts = async () => {
  const response = await fetch(
    `https://6909c69b1a446bb9cc1ff256.mockapi.io/api/products/APIProduct/${id}`
  );
  product.value = await response.json();
  console.log("Berhasil fetch data");
};

onMounted(() => {
  fetchProducts();
});
</script>

<template>
  <h1 class="text-6xl mb-10 text-left">{{ product.title }}</h1>
  <img
    :src="product.image"
    :alt="product.title"
    class="w-150 h-[200] object-cover rounded-2xl ring-2 ring-gray-300 mb-10"
  />
  <div class="text-left flex flex-col gap-4">
    <div class="flex gap-10 items-center">
      <p class="text-5xl text-amber-100">{{ product.price }}</p>
      <p class="font-medium text-2xl">{{ product.category }}</p>
    </div>
    <p class="text-lg">{{ product.description }}</p>
  </div>
</template>
