<script>
export default {
  props: {
    footer: String,
  },
};
</script>

<template>
  <footer class="footer py-3 text-center mt-5 mb-4">
    <router-link to="/about" class="link">About</router-link>&nbsp
    <router-link to="/" class="link">Home</router-link>
    <p class="m-0">Create with ❤️‍🔥 and 🖐 in Denpasar</p>
    <small
      ><a href="https://github.com/primakara-developers"
        >Primakara Developers {{ new Date().getFullYear() }}</a
      ></small
    >
  </footer>
  </template>
