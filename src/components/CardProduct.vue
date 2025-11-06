<script setup>
import { useRouter } from "vue-router";

defineProps({
  product: { type: Object, required: true },
});
</script>

<template>
  <router-link :to="`/product/${product.id}`">
    <section
      class="flex justify-center m-5 w-100 group hover:scale-105 transition duration-300 ease-in-out cursor-pointer"
      v-if="product.image != ''"
    >
      <div
        class="flex flex-col items-center card-product border p-4 rounded-lg shadow-lg"
      >
        <img
          :src="product.image"
          :alt="product.title"
          class="w-full h-64 object-cover"
        />
        <h2
          class="group-hover:text-yellow-200 group-hover:font-bold transition duration-300 ease-in-out"
        >
          {{ product.title }}
        </h2>
        <p
          class="group-hover:text-yellow-50 transition duration-300 ease-in-out"
        >
          {{ product.description }}
        </p>
      </div>
    </section>
  </router-link>
</template>
