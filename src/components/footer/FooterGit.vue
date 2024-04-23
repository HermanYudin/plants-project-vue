<template>
  <div class="footerGit-container" id="app">
    <a class="footerGit-link" :href="'' + anchor">
      <img class="img-git" :src="imgGit" alt="img-git"
    /></a>
    <ul class="footerGit-links">
      <li v-for="(gitLink, index) in gitLinks" :key="index">
        <a class="footerGit-link" :href="'' + anchor">{{ gitLink }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "FooterGit",
  data() {
    return {
      imgGit: require("/src/assets/png/c.png"),
    };
  },
  props: {
    gitLinks: {
      type: Array,
    },
    anchor: {
      type: String,
    },
  },
};
</script>

<style scoped>
.footerGit-container {
  font-size: 20px;
  font-family: "regular";
  margin-left: 111px;
  display: flex;
  align-items: center;
}
.footerGit-link {
  color: black;
  text-decoration: none;
  transition: all 0.2s ease-in-out;
}

.footerGit-link:hover {
  color: #e06733;
}
.footerGit-links {
  list-style-type: none;
  display: flex;
  gap: 20px;
  padding-left: 22px;
}
</style>
