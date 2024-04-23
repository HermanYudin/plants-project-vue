<template>
  <div class="city-card" :class="{ open: isCardOpened }">
    <div class="card-text-wrapper">
      <div class="card-info">
        <div class="info-text">
          <p class="info-paragraph">City:</p>
          <span class="info-discription">{{ cities[index] }}</span>
        </div>
        <div class="info-text">
          <p class="info-paragraph">Phone:</p>
          <span class="telephone">{{ phones[index] }}</span>
        </div>
        <div class="info-text">
          <p class="info-paragraph">Office adress:</p>
          <span class="info-office">{{ addresses[index] }}</span>
        </div>
      </div>
    </div>
    <div class="card-btn-container">
      <button class="card-btn">Call us</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ResSelectApp",
  props: {
    index: {
      type: Number,
      required: true,
    },

    cities: {
      type: Array,
      default: () => [],
    },

    phones: {
      type: Array,
      default: () => [],
    },

    addresses: {
      type: Array,
      default: () => [],
    },
    isCardOpened: {
      type: Boolean,
    },
  },
};
</script>

<style scoped>
.city-card {
  display: none;
  width: 450px;
  height: 212px;
  background-color: #edf2ec;
  margin-top: 47px;
  border: 1px solid #717171;
  border-radius: 20px;
  text-align: center;
}

.city-card.open {
  display: block;
}

.card-text-wrapper {
  text-align: justify;
  padding: 25px 0 0 35px;
}

.card-info {
  font-size: 16px;
  font-family: "regular";
}

.info-text {
  display: flex;
  padding-bottom: 21px;
  letter-spacing: 1px;
}

.info-paragraph {
  width: 130px;
  color: #010201;
  font-size: 16px;
  margin: 0;
}

.telephone {
  color: #636060;
  letter-spacing: 1px;
  font-weight: 400;
}

.info-office {
  color: #636060;
  letter-spacing: 1px;
  font-weight: 400;
}

.info-discription {
  color: #636060;
  letter-spacing: 1px;
  font-weight: 400;
}

.card-btn-container {
  padding: 7px 0 15px;
  display: flex;
  justify-content: center;
}

.card-btn {
  font-family: "inika-bold";
  min-width: 122px;
  min-height: 25px;
  font-size: 10px;
  color: #717171;
  border-radius: 5px;
  border: 1px solid #e06733;
  cursor: pointer;
  transition: all 0.4s ease;
}

.card-btn:hover {
  background-color: #e06733;
  color: #fff;
}
</style>
