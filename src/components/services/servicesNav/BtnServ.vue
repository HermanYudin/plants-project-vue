<template>
  <div class="services-btn-container">
    <button
      class="serv-button"
      v-for="(btn, index) in btns"
      :key="index"
      :class="{ active: activeBtns.includes(btn) }"
      @click="setActiveBtn(btn), setActiveCard()"
    >
      {{ btn }}
    </button>
  </div>
</template>

<script>
export default {
  name: "BtnServ",
  props: {
    btns: {
      type: Array,
    },
    activeBtns: {
      type: Array,
    },
    setActiveBtn: {
      type: Function,
    },
  },
  methods: {
    setActiveCard() {
      this.$emit("set-btn", this.activeBtns);
    },
  },
};
</script>

<style scoped>
.services-btn-container {
  display: flex;
  gap: 43px;
}

.serv-button {
  border: 1px solid #e06733;
  padding: 10px 45px 10px 45px;
  border-radius: 5px;
  cursor: pointer;
  color: #e06733;
  font-size: 20px;
  font-family: "inika-regular";
  transition: all;
  transition-duration: 0.5s;
}

.serv-button:hover,
.serv-button.active {
  background-color: #e06733;
  color: white;
  border: 1px solid #e06733;
}
</style>
