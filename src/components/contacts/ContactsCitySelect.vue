<template>
  <div
    @click="toggleOpened()"
    :class="{ open: isOpened }"
    class="select-dropdown"
  >
    <span class="city-selected">{{ cityValue }}</span>
    <div :class="{ open: isOpened }" class="circle-dropdown"></div>
    <ul :class="{ open: isOpened }" class="select-options">
      <li
        @click="getCityValue(index)"
        v-for="(city, index) in cities"
        :key="index"
        class="city-select"
      >
        {{ city }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SelectApp",
  props: {
    cities: {
      type: Array,
      default: () => [],
    },
  },

  data() {
    return {
      cityValue: "City",
      isOpened: false,
    };
  },
  methods: {
    toggleOpened() {
      this.isOpened = !this.isOpened;
    },
    getCityValue(index) {
      this.cityValue = this.cities[index];
      this.$emit("city-change", index);
    },
  },
};
</script>

<style scoped>
.select-dropdown {
  margin-top: 147px;
  position: relative;
  width: 450px;
  height: 50px;
  background-color: #d6e7d2;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 5px;
}

.select-dropdown.open {
  background-color: #c1e698;
  box-shadow: none;
}

.city-selected {
  display: flex;
  align-items: center;
  padding: 5px 0 5px 20px;
  color: #717171;
  font-size: 20px;
  height: 50px;
  letter-spacing: 1px;
  font-family: "Inter", normal, sans-serif;
  line-height: 1.6;
}

.circle-dropdown {
  position: absolute;
  background-repeat: no-repeat;
  background-image: url("/src/assets/png/down-gray.png");
  width: 17px;
  height: 17px;
  top: 36%;
  right: 8%;
  transition: all 0.2s ease;
}

.circle-dropdown.open {
  background-repeat: no-repeat;
  background-image: url("/src/assets/png/up-green.png");
}

.select-options {
  display: none;
  font-size: 16px;
  font-family: "Inter", normal, sans-serif;
  color: #499a18;
  background-color: #d6e7d2;
  padding: 36px 50px 0 25px;
  transition: all 0.5s ease;
}

.select-options.open {
  display: block;
  transition: all 0.3s ease-in-out;
  margin: 0 auto;
}

.city-select {
  text-decoration: none;
  position: relative;
  padding-bottom: 22px;
  line-height: 1.6;
  letter-spacing: 1px;
  cursor: pointer;
  transition: all 0.3s ease;
  list-style-type: none;
}

.city-select::after {
  content: "";
  position: absolute;
  width: 380px;
  height: 0.5px;
  background-color: #d9d9d9;
  bottom: 22px;
  left: 0;
}

.city-select:hover {
  color: #717171;
  transform: translateY(-2px) scaleZ(-97%);
}

.city-select:hover::after {
  background-color: #717171;
}
</style>
