<template>
  <div class="footerSocial-container">
    <ul class="social-list">
      <li class="social-item" v-for="(social, index) in socials" :key="index">
        <a class="social-link" :href="social.link">
          <img class="social-img" :src="social.img" alt="social-img" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "footerMain",
  props: {
    socials: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style scoped>
.footerSocial-container {
  margin-right: 109px;
  display: flex;
}

.social-list {
  display: flex;
  list-style-type: none;
  gap: 20px;
}
</style>
