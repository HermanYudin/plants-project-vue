<template>
  <div class="btn-container">
    <button class="button" :class="{ prices: prices }">
      {{ buttonText }}
    </button>
  </div>
</template>

<script>
export default {
  name: "BtnBtn",
  data() {
    return {
      hover: true,
    };
  },
  props: {
    buttonText: {
      type: String,
      default: "LEARN MORE", // Значение по умолчанию для текста кнопки
    },
    prices: {
      type: Boolean,
      default: true,
    },
  },
};
</script>

<style scoped>
.button {
  color: black;
  font-size: 16px;
  font-family: "regular";
  padding: 11px 25px 11px 27px;
  border: 2px solid #e06733;
  border-radius: 10px;
  margin-top: 26px;
  text-align: center;
  transition: all;
  transition-duration: 0.7s;
}

.button-link {
  text-decoration: none;
  color: black;
  transition: all;
  transition-duration: 0.7s;
}

.button:hover .button-link {
  color: #e06733;
}

.button:hover {
  cursor: pointer;
  border-color: #499a18;
  color: #e06733;
  border-radius: 20px;
  transform: scale(1.06);
}

.prices {
  margin-right: 2px;
  padding: 11px 35px 11px 35px;
}

.prices:hover {
  background-color: #e06733;
  color: white;
  border-radius: 10px;
  border: 2px solid #e06733;
}
</style>
