<script>
import Title from "@/components/Title.vue";
import Loading from "@/views/Loading.vue";

export default {
  components: { Title, Loading },
  setup() {
    return { Title };
  },
  data() {
    return {
      loading: true,
    };
  },
};
</script>

<template>
  <Loading />
  <router-view />
</template>

<style>
body {
  background-color: #f5f5f5;
}
</style>
