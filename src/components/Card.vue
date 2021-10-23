<script>
export default {
  props: {
    category: { type: String, default: "" },
    description: { type: String, default: "" },
    image: { type: String, default: "" },
    link: { type: String, default: "" },
  },
  setup() {
    const truncateText = (str, length, ending) => {
      if (length == null) {
        length = 100;
      }
      if (ending == null) {
        ending = "...";
      }
      if (str.length > length) {
        return str.substring(0, length - ending.length) + ending;
      } else {
        return str;
      }
    };

    return { truncateText };
  },
};
</script>

<template>
  <div class="col">
    <div class="card h-100 card-bg">
      <img :src="image" class="card-img-top" alt="nice pic" />
      <div class="card-body">
        <h3 class="card-title">{{ category }}</h3>
        <p class="card-text">
          {{ truncateText(description, 100) }}
        </p>
      </div>
      <div class="card-footer bg-transparent border-none">
        <router-link class="btn btn-success" :to="link">Read more</router-link>
      </div>
    </div>
  </div>
</template>

<style>
.card {
  padding-bottom: 8px;
  border: none !important;
}
.card-bg {
  box-shadow: 0 0 30px rgba(31, 45, 61, 0.125);
  border-radius: 5px;
}
.card-footer {
  border: none !important;
}
</style>
