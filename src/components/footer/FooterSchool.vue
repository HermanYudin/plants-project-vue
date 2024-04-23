<template>
  <div class="footerSchool-container" id="app">
    <a class="footerSchool-link" :href="'' + anchor"> {{ text }}</a>
  </div>
</template>

<script>
export default {
  name: "FooterSchool",
  props: {
    anchor: {
      type: String,
    },
    text: {
      type: String,
    },
  },
};
</script>

<style scoped>
.footerSchool-container {
  margin-left: 60px;
}

.footerSchool-link {
  color: black;
  text-decoration: none;
  font-size: 20px;
  font-family: "regular";
  transition: all;
  transition-duration: 0.2s;
}

.footerSchool-link:hover {
  color: #e06733;
}
</style>
