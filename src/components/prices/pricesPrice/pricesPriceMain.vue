<template>
  <div class="prices-container">
    <PricesTitle />
    <pricesAllPrices />
  </div>
</template>

<script>
import PricesTitle from "./PricesTitle.vue";
import pricesAllPrices from "./PricesAllPrices.vue";

export default {
  name: "pricesPriceMain",
  components: {
    PricesTitle,
    pricesAllPrices,
  },
};
</script>

<style scoped>
.prices-container {
  margin: 5px auto auto 110px;
}
</style>
