<template>
  <div class="prices-disc-title-container">
    <h1 class="prices-disc-title">
      <span
        v-for="(word, index) in title.split(' ')"
        :key="index"
        :style="{ color: word === 'gardeners' ? '#499A18' : 'black' }"
        >{{ word }}
      </span>
    </h1>
  </div>
</template>

<script>
export default {
  name: "PricesDiscTitle",
  data() {
    return {
      title: "Our best gardeners are ready to help you",
    };
  },
};
</script>

<style scoped>
.prices-disc-title {
  font-family: "bold";
  font-size: 40px;
  text-align: end;
  margin-bottom: 19px;
}
</style>
