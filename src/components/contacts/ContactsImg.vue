<template>
  <div class="contacts-img-container">
    <img class="img-contacts" :src="imgContacts" alt="img-contacts" />
  </div>
</template>

<script>
export default {
  name: "contactsImg",
  data() {
    return {
      imgContacts: require("/src/assets/png/woman.png"),
    };
  },
};
</script>

<style scoped>
.img-contacts {
  max-width: 400px;
  width: 100%;
  margin-top: 53px;
  margin-left: 108px;
  display: block;
}
</style>
