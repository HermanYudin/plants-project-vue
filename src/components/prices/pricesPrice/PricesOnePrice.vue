<template>
  <div
    class="prices-select"
    :class="{ selected: isSelected }"
    @click="$emit('dropdown-select')"
  >
    <div class="main-btn">
      <h1 class="prices-select-header">{{ item.title }}</h1>
      <button class="prices-select-mini-btn">
        <img
          :src="!isSelected ? imgDown : imgUp"
          :class="{ selected: isSelected }"
        />
      </button>
    </div>
    <div class="prices-select-discription" :class="{ selected: isSelected }">
      <div class="prices-select-text-line"></div>
      <p class="prices-select-text">
        {{ item.text }}
      </p>
      <span class="prices-select-price"
        ><font color="#E06733"
          ><font size="3"
            ><font family="bold">${{ item.price }}</font></font
          ></font
        >/per hour</span
      >
      <button @click="$emit('dropdown-select')" class="prices-select-button">
        Order
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "PricesApp2",
  data() {
    return {
      isSelected: false,
      imgDown: require("/src/assets/png/down.png"),
      imgUp: require("/src/assets/png/up.png"),
    };
  },
  props: {
    item: {
      type: Object,
      default: () => ({}),
    },

    isOpen: {
      type: Boolean,
      default: false,
    },
  },

  watch: {
    isOpen(newValue) {
      this.isSelected = newValue;
      console.log(this.isSelected);
    },
  },
};
</script>

<style scoped>
.prices-select {
  max-width: 250px;
  width: 100%;
  max-height: 50px;
  overflow-y: hidden;
  border-radius: 20px;
  background-color: #edf2ec;
  padding: 12px 121px 12px 38px;
  border: none;
  outline: none;
  cursor: pointer;
  transition-duration: 0.5s;
  transition-property: max-height, background-color;
}

.prices-select-mini-btn {
  outline: none;
  border: none;
  cursor: pointer;
  margin-left: 50px;
}

.prices-select.selected {
  max-height: 154px;
}

.main-btn {
  display: flex;
  align-items: center;
}

.prices-select-header {
  font-family: "bold";
  font-size: 20px;
  text-align: start;
  margin: auto;
  min-width: 100px;
}

.prices-select:nth-child(1n + 2) {
  margin-top: 32px;
}

.prices-select-text {
  min-width: 172px;
  font-size: 10px;
  font-family: "regular";
  margin-top: 6px;
  line-height: 10px;
}

.prices-select-text-line {
  display: block;
  width: 100%;
  min-height: 0.5px;
  margin-right: auto;
  background-color: #aea1a1;
  margin-bottom: 7px;
}

.prices-select-price {
  margin-top: 6px;
  font-size: 12px;
}

.prices-select-button {
  max-width: 86px;
  width: 100%;
  max-height: 25px;
  background-color: white;
  color: #717171;
  font-size: 14px;
  font-family: "bold";
  border-radius: 20px;
  outline: none;
  border: 1px solid transparent;
  cursor: pointer;
  display: flex;
  justify-content: flex-start;
  margin-top: 10px;
  padding: 3px 20px 3px 20px;
  transition: all;
  transition-duration: 0.5s;
}

.prices-select-button:hover {
  background-color: white;
  color: #499a18;
  border: 1px solid #717171;
}

.prices-select-discription {
  opacity: 0;
  z-index: 1;
  position: relative;
  transition: all;
  transition-duration: 0.8s;
}

.prices-select-discription.selected {
  opacity: 1;
  background-repeat: no-repeat;
  background-position: right 40px top 17px;
  background-size: 16px;
}
</style>
