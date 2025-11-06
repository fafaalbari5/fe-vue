<script setup lang="ts">
import CardProduct from '@/components/CardProduct.vue';
import { onMounted, ref } from 'vue'

const product = ref([])
const fetchProducts = async ()=> {
    const response = await fetch('https://6909c69b1a446bb9cc1ff256.mockapi.io/api/products/APIProduct')
    product.value = await response.json()
    console.log("Berhasil fetch data")
}

onMounted(() => {
    fetchProducts()
})

</script>

<template>
    <div class="text-center mb-4">
        <h1>Home Page</h1>
        <p>Ini adalah halaman Home</p>
    </div>
    <div class="flex justify-center mb-4">
        <h2>Products</h2>
    </div>
    <div class="flex flex-row flex-wrap justify-center">
        <div v-for="product in product" :key="product.id">
            <CardProduct :product="product" />
        </div>
    </div>
</template>