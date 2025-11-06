<script>
export default {
  data() {
    return {
      nama_mahasiswa: ["Me", "Metoo", "MeAgain"],
    };
  },
};
</script>

<template>
  <nav
    class="flex bg-primary dark:bg-primary-dark text-text-normal dark:text-text-dark p-4 items-center"
  >
    <div class="brand">
      <img src="/favicon.ico" alt="logo" />
      <span>Vuejstia24</span>
    </div>
    <ul class="flex list-none gap-4 justify-end ml-auto">
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About</router-link></li>
      <li><router-link to="/contact">Contact</router-link></li>
    </ul>
  </nav>
  <p v-html="nama_mahasiswa"></p>
</template>
