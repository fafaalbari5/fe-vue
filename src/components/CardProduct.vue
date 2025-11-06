<script setup>
defineProps({
    product: {
        type: Object,
        required: true
    }
})

</script>

<template>
    <section class="flex justify-center m-2 bg-primary dark:bg-primary-dark text-text-normal dark:text-text-dark w-80 p-2 rounded-lg">
        <div class="flex flex-col items-center card-product rounded-lg w-full border">
            <img :src="product.image" alt="image" class="w-full h-50 object-cover rounded-lg" />
            <h2>{{ product.title }}</h2>
            <p>{{ product.price }}</p>
            <router-link :to="`/product/${product.id}`" class="mt-2 px-4 py-2 bg-secondary dark:bg-secondary-dark text-white rounded-lg hover:opacity-80">
                View Details
            </router-link>
        </div>
    </section>
</template>
