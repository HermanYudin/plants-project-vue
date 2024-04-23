<template>
  <div class="contacts-title-container">
    <h1 class="contacts-title">{{ title }}</h1>
  </div>
</template>

<script>
export default {
  name: "ContactsTitle",
  data() {
    return {
      title: "Contact us",
    };
  },
};
</script>

<style scoped>
.contacts-title {
  color: #499a18;
  font-family: "inika-bold";
  font-size: 40px;
  margin-top: 60px;
  margin-left: 44px;
}
</style>
