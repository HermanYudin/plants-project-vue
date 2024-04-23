<template>
  <div class="prices-main-container">
    <pricesPriceMain />
    <pricesDiscMain />
  </div>
</template>

<script>
import pricesPriceMain from "../prices/pricesPrice/pricesPriceMain.vue";
import pricesDiscMain from "../prices/pricesDisc/pricesDiscMain.vue";

export default {
  name: "pricesMain",
  components: {
    pricesPriceMain,
    pricesDiscMain,
  },
};
</script>

<style scoped>
.prices-main-container {
  min-width: 1440px;
  width: 100%;
  background-color: white;
  display: flex;
  justify-content: space-between;
  padding-bottom: 116px;
}
</style>
