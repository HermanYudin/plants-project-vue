<template>
  <div class="home-text-container">
    <p v-if="about" class="home-text" :class="{ about: about }">
      {{ textAbout }}
    </p>
    <p v-else class="home-text">{{ textHome }}</p>
  </div>
</template>

<script>
export default {
  name: "DiscTextHome",
  props: {
    about: {
      type: Boolean,
    },
    textHome: {
      type: String,
    },
    textAbout: {
      type: String,
    },
  },
};
</script>

<style scoped>
.home-text {
  font-size: 20px;
  color: gray;
  font-family: "regular";
  margin-top: 40px;
  line-height: 35px;
  box-shadow: 10px 5px 5px #499a18;
}

.about {
  font-size: 20px;
  color: gray;
  font-family: "regular";
  line-height: 30px;
  /* padding-top: 4px; */
  box-shadow: 10px 5px 5px #e06733;
  min-width: 600px;
}
</style>
