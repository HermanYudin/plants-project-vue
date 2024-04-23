<template>
  <div class="footer-main-container">
    <FooterGit :gitLinks="gitLinks" :anchor="anchor" />
    <FooterSchool :text="text" :anchor="anchor" />
    <FooterSocial :socials="socials" />
  </div>
</template>

<script>
import FooterGit from "../footer/FooterGit";
import FooterSchool from "../footer/FooterSchool";
import FooterSocial from "../footer/FooterSocial";

export default {
  name: "footerMain",
  components: {
    FooterGit,
    FooterSchool,
    FooterSocial,
  },
  data() {
    return {
      gitLinks: ["2024", "github"],
      anchor: "https://github.com/HermanYudin",
      text: "Rolling Scopes School",
      socials: [
        {
          link: "http://instagram.com/",
          img: require("/src/assets/png/inst 1.png"),
        },
        {
          link: "http://facebook.com/",
          img: require("/src/assets/png/fb 1.png"),
        },
        {
          link: "http://twitter.com/",
          img: require("/src/assets/png/tw 1.png"),
        },
        {
          link: "http://pinterest.com/",
          img: require("/src/assets/png/pinterest 1.png"),
        },
      ],
    };
  },
};
</script>

<style scoped>
.footer-main-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  min-width: 1440px;
  width: 100%;
  padding-top: 30px;
  padding-bottom: 30px;
}
</style>
