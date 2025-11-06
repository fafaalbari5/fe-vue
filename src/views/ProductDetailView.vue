<script setup>
import { onMounted, ref } from 'vue'
import { useRoute } from 'vue-router'

const product = ref([])
const route = useRoute()
const fetchProducts = async () => {
    const response = await fetch(`https://6909c69b1a446bb9cc1ff256.mockapi.io/api/products/APIProduct/${route.params.id}`)
    product.value = await response.json()
    console.log("Berhasil fetch data")
}

onMounted(() => {
    fetchProducts()
})

</script>

<template>
    <div class="text-center mb-4">
        <h1>Product Detail Page</h1>
        <p>Ini adalah halaman detail produk</p>
    </div>
    <div class="">
        <div class="text-left w-[400px] h-auto object-cover">
            <img :src="product.image" :alt="product.title" />
            <h1>{{ product.title }}</h1>
            <h2>{{ product.price }}</h2>
            <h2>{{ product.category }}</h2>
            <p>{{ product.description }}</p>
        </div>
    </div>
</template>