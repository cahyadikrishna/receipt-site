<script>
import { ref } from "vue";
import Title from "@/components/Title.vue";
import ReceiptDetail from "@/views/ReceiptDetail.vue";
import Footer from "@/components/Footer.vue";
import api from "@/api/api.js";
import { useRoute } from "vue-router";

export default {
  name: "Detail",
  components: {
    Title,
    ReceiptDetail,
    Footer,
  },
  setup() {
    const route = useRoute();
    const detailData = ref([]);

    console.log(route.params.id);

    async function getDetail() {
      const response = await api(`/lookup.php?i=${route.params.id}`);
      detailData.value = response.meals;
      console.log(detailData);
    }
    getDetail();

    return { Title, ReceiptDetail, Footer, detailData, route };
  },
};
</script>

<template>
  <div class="container d-flex flex-column justify-content-center">
    <Title title="Foody Receipt"></Title>

    <router-view></router-view>

    <!-- Receipt detail -->
    <ReceiptDetail
      v-for="data in detailData"
      :key="data.idMeal"
      :category="data.strCategory"
      :instructions="data.strInstructions"
      :image="data.strMealThumb"
      :area="data.strArea"
      :mealname="data.strMeal"
    />
    <!-- Footer component -->
    <Footer />
  </div>
</template>

<style></style>
