<script>
import { ref } from "vue";
import Title from "@/components/Title.vue";
import Loader from "@/components/Loader.vue";

export default {
  components: { Title, Loader },
  setup() {
    const loading = ref(false);
    function doUpdateLoading(status){
      console.log(status);
      loading.value = status;
    }
    return { Title, Loader, loading, doUpdateLoading };
  },
};
</script>

<template>
  <Loader v-if="loading" />
  <div v-show="loading === false">
    <router-view @loadingStatus="doUpdateLoading"/>
  </div>
</template>

<style>
body {
  background-color: #f5f5f5;
}
</style>
