<script>
import Title from "@/components/Title.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "About",
  components: {
    Title,
    Footer,
  },
  setup() {
    return { Title, Footer };
  },
};
</script>
<template>
  <Title title="About" />
  <router-view />
  <p>About</p>
  <Footer />
</template>
