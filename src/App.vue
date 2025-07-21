<template>
  <div id="app">
    <Navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
  components: {
    Navbar,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
html {
  scroll-behavior: smooth;
  font-family: 'Segoe UI', sans-serif;
}

section {
  scroll-margin-top: 100px; /* Adjust based on navbar height */
}

body {
  margin: 0;
  font-family: 'Inter', sans-serif;
  background-color: #0f2027;
  color: white;
  scroll-behavior: smooth;
}
</style>
