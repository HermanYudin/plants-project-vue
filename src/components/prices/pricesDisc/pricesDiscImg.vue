<template>
  <div class="img-disc-prices-container">
    <img class="img-disc-prices" :src="imgDiscPrices" alt="img-disc-prices " />
  </div>
</template>

<script>
export default {
  name: "imgDiscPrices",
  data() {
    return {
      imgDiscPrices: require("/src/assets/images/leafs.jpg"),
    };
  },
};
</script>

<style scoped>
.img-disc-prices {
  max-height: 175px;
  max-width: 152px;
  width: 100%;
  margin-top: 39px;
  margin-left: 300px;
}
</style>
