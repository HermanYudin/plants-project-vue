<template>
  <article class="services-card-container">
    <div class="img-container">
      <img class="service-img" :src="card.img" />
    </div>
    <div class="title-container">
      <h1 class="services-title">{{ card.title }}</h1>
    </div>
    <div class="text-container">
      <p class="services-text">{{ card.text }}</p>
    </div>
  </article>
</template>

<script>
export default {
  name: "ServicesCard",
  props: {
    card: {
      type: Object,
      default: () => ({}),
    },
  },
};
</script>

<style scoped>
.services-card-container {
  width: 30%;
  text-align: center;
  margin: 0 auto;
  filter: blur(2px);
  transition: all;
  transition-duration: 1s;
}

.service-img {
  border-radius: 20px 20px 0 0;
}

.services-title {
  margin-top: 5px;
  font-size: 20px;
  font-weight: bold;
  font-family: "bold";
  color: #e06733;
}

.services-text {
  margin-top: -5px;
  font-size: 16px;
  font-family: "regular";
}

.services-card-container.active {
  filter: blur(0);
}

.services-card-container:nth-child(3n + 1) {
  padding-left: 68px;
}

.services-card-container:nth-child(3n + 3) {
  padding-right: 69px;
}

.services-card-container:nth-child(1n + 4) {
  margin-top: 70px;
}
</style>
