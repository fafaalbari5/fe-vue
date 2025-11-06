<script setup>
defineProps({
  product: { type: Object, required: true },
});
</script>

<template>
  <section class="flex justify-center m-5 w-100" v-if="product.image != ''">
    <div
      class="flex flex-col items-center card-product border p-4 rounded-lg shadow-lg"
    >
      <img
        :src="product.image"
        :alt="product.title"
        class="w-full h-64 object-cover"
      />
      <h2>{{ product.title }}</h2>
      <p>{{ product.description }}</p>
    </div>
  </section>
</template>
