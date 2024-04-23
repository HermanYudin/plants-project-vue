<template>
  <div class="services-title-container">
    <h1 class="services-title">{{ title }}</h1>
  </div>
</template>

<script>
export default {
  name: "TitleServices",
  data() {
    return {
      title: "Service and our projects",
    };
  },
};
</script>

<style scoped>
.services-title {
  font-size: 40px;
  color: #499a18;
  min-width: 300px;
  width: 100%;
  font-family: "inika-regular";
  font-weight: normal;
}
</style>
