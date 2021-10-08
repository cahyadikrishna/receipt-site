<script>
import { ref } from "vue";
import Title from "@/components/Title.vue";
import Card from "@/components/Card.vue";
import { useRoute } from "vue-router";
import { computed } from "vue";

export default {
  name: "App",
  components: {
    Title,
    Card,
  },
  setup() {
    const route = useRoute();
    const receiptData = ref([]);

    console.log(route.params.category)

    async function getReceipt() {
      const response = await fetch(
        `https://www.themealdb.com/api/json/v1/1/filter.php?c=${route.params.category}`
      );
      const json = await response.json();
      receiptData.value=json.meals
      console.log(receiptData);
    }
    getReceipt();

    return { Title, Card, receiptData, route };
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
        v-for="data in receiptData"
        :key="data.idMeal"
        :category="data.strMeal"
        :image="data.strMealThumb"
      />
    </div>
    ><!-- Footer component -->
  </div>
</template>

<style></style>
