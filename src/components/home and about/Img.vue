<template>
  <div class="img-container">
    <img
      class="img-home"
      alt="img-home"
      :src="!about ? imgHome : imgAbout"
      :about="about"
      :class="{ about: about }"
    />
  </div>
</template>

<script>
export default {
  name: "ImgHome",
  props: {
    about: {
      type: Boolean,
    },
    imgHome: {
      type: String,
    },
    imgAbout: {
      type: String,
    },
  },
};
</script>

<style scoped>
.img-home {
  max-width: 448px;
  width: 100%;
  margin-top: 62px;
  margin-left: 109px;
  margin-bottom: 62px;
}

.about {
  max-width: 464px;
  width: 100%;
  margin: 93px 109px 72px auto;
}
</style>
