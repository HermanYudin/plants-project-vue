<template>
  <div>
    <img class="logo" :src="logo" alt="logo" />
  </div>
</template>

<script>
export default {
  name: "LogoHeader",
  data() {
    return {
      logo: require("/src/assets/svg/logo.svg"),
    };
  },
};
</script>

<style scoped>
.logo {
  width: 80px;
  margin-left: 110px;
  transition: all;
  transition-duration: 1s;
}

.logo:hover {
  width: 90px;
  cursor: pointer;
}
</style>
