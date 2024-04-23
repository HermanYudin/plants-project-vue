<template>
  <div class="prices-title-container">
    <h1 class="prices-title">{{ title }}</h1>
  </div>
</template>

<script>
export default {
  name: "PricesTitle",
  data() {
    return {
      title: "Prices",
    };
  },
};
</script>

<style scoped>
.prices-title {
  font-weight: bold;
  font-family: "bold";
  font-size: 40px;
}
</style>
