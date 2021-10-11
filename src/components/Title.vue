<script>
export default {
  props: {
    title: String,
  },
};
</script>

<template>
  <p class="text-center fs-1 fw-bold text-success mt-5">{{ title }}</p>
  <div class="d-flex justify-content-center">
    <router-link to="/" class="link text-success"><b>Home </b></router-link>
    &nbsp
    <router-link to="/about" class="link text-success"
      ><b> About</b></router-link
    >
  </div>
</template>
