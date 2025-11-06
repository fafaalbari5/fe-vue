<script setup>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
import CardProduct from "./components/CardProduct.vue";
import { ref } from "vue";

const isDark = ref(false);
const toggleTheme = () => {
  isDark.value = !isDark.value;
};
</script>

<template>
  <div
    id="app"
    :class="{ dark: isDark }"
    class="typography bg-background dark:bg-background-dark text-text-normal dark:text-text-dark"
  >
    <Navbar />
    <div class="text-right text-text-normal dark:text-text-dark p-4">
      <button @click="toggleTheme">
        {{ isDark ? "Dark Mode" : "Light Mode" }}
      </button>

      <router-view />
    </div>
    <h1>Hello Its me</h1>
    <Footer />
  </div>
</template>

<style scoped>
@import "tailwindcss";
</style>
