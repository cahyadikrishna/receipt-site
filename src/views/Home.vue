<script>
import { ref } from "vue";
import Title from "@/components/Title.vue";
import Footer from "@/components/Footer.vue";
import Card from "@/components/Card.vue";
import api from "@/api/api.js";

export default {
  name: "Home",
  components: {
    Title,
    Card,
    Footer,
  },
  setup() {
    const categoryData = ref([]);

    async function getData() {
      const response = await api("/categories.php");
      // console.log(json);
      categoryData.value = response.categories;
      // console.log(categoryData.value);
    }
    getData();

    return { Title, Card, Footer, categoryData };
  },
};
</script>

<template>
  <div class="container d-flex flex-column justify-content-center">
    <Title title="Foody Receipt"></Title>

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
        v-for="data in categoryData"
        :key="data.idCategory"
        :category="data.strCategory"
        :description="data.strCategoryDescription"
        :image="data.strCategoryThumb"
        :link="`/menu/${data.strCategory}`"
      />
    </div>
    <!-- Footer component -->
    <Footer />
  </div>
</template>

<style></style>
