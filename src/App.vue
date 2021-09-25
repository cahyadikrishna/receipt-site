<script>
import { ref } from "vue";
import Title from "./components/Title.vue";
import Card from "./components/Card.vue";
import { computed } from "vue";

export default {
  name: "App",
  components: {
    Title,
    Card,
  },
  setup() {
    const categoryData = ref([]);

    async function getData(){
    const response = await fetch("https://www.themealdb.com/api/json/v1/1/categories.php")
        const json = await response.json()
        console.log(json)
        categoryData.value = json.categories;
        console.log(categoryData.value)
    }
    getData()

    return {Title, Card, categoryData};
  },
};
</script>

<template>
  <div class="container d-flex flex-column justify-content-center">
    <!-- Search bar --><Title title="Foody Receipt"></Title>
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
      <Card v-for="data in categoryData" :key="data.idCategory" 
      :category="data.strCategory" 
      :description="data.strCategoryDescription"
      :image="data.strCategoryThumb" />
    </div>
    ><!-- Footer component -->
    <footer class="footer py-3 text-center mt-5 mb-4">
      <p class="m-0">Create with \ \\\ ❤️‍🔥 and 🖐 in Denpasar</p>
      <small
        ><a href="https://github.com/primakara-developers"
          >Primakara Developers {{ new Date().getFullYear() }}</a
        ></small
      >
    </footer>
  </div>
</template>

<style></style>
