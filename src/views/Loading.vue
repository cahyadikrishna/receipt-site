<script>
export default {
  data() {
    loading: false;
  },
};
</script>
<template>
  <div
    class="d-flex justify-content-center align-items-center"
    style="height: 100vh"
    v-show="loading"
  >
    <div
      class="spinner-border text-success"
      style="width: 3rem; height: 3rem"
      role="status"
    >
      <span class="visually-hidden">Loading...</span>
    </div>
  </div>
</template>
