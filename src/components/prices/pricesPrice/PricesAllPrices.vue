<template>
  <div class="prices-select-container">
    <PricesOnePrice
      v-for="(item, index) in dropdowns"
      :key="index"
      :item="item"
      :is-open="activeDropdown === index"
      @dropdown-select="setActiveDropdown(index)"
    />
  </div>
</template>

<script>
import PricesOnePrice from "./PricesOnePrice.vue";

export default {
  name: "pricesAllPrices",
  components: {
    PricesOnePrice,
  },
  data() {
    return {
      activeDropdown: null,
      dropdowns: [
        {
          title: "Basics",
          price: "15",
          text: "Release of Letraset sheets containing Lorem Ipsum passages, and more recently",
        },

        {
          title: "Standard",
          price: "25",
          text: "Release of Letraset sheets containing Lorem Ipsum passages, and more recently",
        },

        {
          title: "Pro care",
          price: "35",
          text: "Release of Letraset sheets containing Lorem Ipsum passages, and more recently",
        },
      ],
    };
  },
  methods: {
    setActiveDropdown(index) {
      if (this.activeDropdown === index) {
        this.activeDropdown = null; // Если текущий индекс уже активен, то закрываем элемент
      } else {
        this.activeDropdown = index; // Иначе делаем текущий элемент активным
      }
    },
  },
};
</script>

<style scoped>
.prices-select-container {
  /* display: flex;
  flex-wrap: wrap; */
  max-width: 332px;
  width: 100%;
  border: 1px solid #e3e1d5;
  padding: 37px 41px 35px 40px;
  border-radius: 20px;
  margin-top: 56px;
}
</style>
