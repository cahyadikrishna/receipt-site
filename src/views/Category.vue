<script>
import { ref } from "vue";
import Title from "@/components/Title.vue";
import Card from "@/components/Card.vue";
import Footer from "@/components/Footer.vue";
import api from "@/api/api.js";
import { useRoute } from "vue-router";

export default {
  name: "Category",
  components: {
    Title,
    Card,
    Footer,
  },
  setup(props, {emit}) {
    const route = useRoute();
    const menuData = ref([]);

    async function getMenu() {
      emit("loadingStatus", true);
      const response = await api(`/filter.php?c=${route.params.category}`);
      menuData.value = response.meals;
      emit("loadingStatus", false);
    }
    getMenu();

    return { Title, Card, Footer, menuData, route };
  },
};
</script>

<template>
  <div class="container d-flex flex-column justify-content-center">
    <Title :title="route.params.category"></Title>

    <router-view></router-view>

    <!-- Search bar -->
    <div class="row mt-2 mb-4">
      <div class="col-10">
        <input
          class="form-control form-control-lg"
          type="text"
          placeholder="Search here..."
        />
      </div>
      <div class="col-2">
        <button class="btn btn-outline-primary btn-lg w-100" type="button">
          🔍 Search
        </button>
      </div>
    </div>
    <!-- Card component list -->
    <div class="row row-cols-1 row-cols-md-5 g-4 mt-3">
      <Card
        v-for="data in menuData"
        :key="data.idMeal"
        :category="data.strMeal"
        :description="data.strDescription"
        :image="data.strMealThumb"
        :link="`/detail/${data.idMeal}`"
      />
    </div>
    <!-- Footer component -->
    <Footer />
  </div>
</template>

<style></style>
