<template>
  <div class="prices-disc-main-container">
    <PricesDiscTitle />
    <a href="#Contacts"><Btn buttonText="Contact us" :prices="!prices" /></a>
    <PricesDiscImg />
  </div>
</template>

<script>
import PricesDiscTitle from "./pricesDiscTitle.vue";
import Btn from "/src/components/Btn";
import PricesDiscImg from "./pricesDiscImg.vue";

export default {
  name: "PricesDiscMain",
  components: {
    PricesDiscTitle,
    Btn,
    PricesDiscImg,
  },
  data() {
    return {
      title: "Our best gardeners are ready to help you",
    };
  },
  props: {
    prices: {
      type: Boolean,
    },
  },
};
</script>

<style scoped>
.prices-disc-main-container {
  max-width: 452px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  margin: 6px 110px auto auto;
}
.prices-disc-btn {
  margin-left: 290px;
}
</style>
