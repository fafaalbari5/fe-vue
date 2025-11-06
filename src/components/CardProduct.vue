<script setup>
defineProps({
    product: {
        type: Object,
        required: true
    }
})

</script>

<template>
    <section class="flex justify-center m-2 bg-primary dark:bg-primary-dark text-text-normal dark:text-text-dark p-10 rounded-lg w-60">
        <div class="flex flex-col items-center border rounded-lg shadow-lg">
            <img :src="product.image" alt="image" class="w-full h-40 object-cover rounded-lg" />
            <h2>{{ product.title }}</h2>
            <p>{{ product.price }}</p>
        </div>
    </section>
</template>
