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
        </div>
    </section>
</template>
