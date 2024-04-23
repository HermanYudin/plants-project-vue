<template>
  <header class="header">
    <div class="container">
      <LogoHeader />
      <NavHeader :links="links" />
    </div>
  </header>
</template>

<script>
import LogoHeader from "../header/LogoHeader";
import NavHeader from "../header/NavHeader";

export default {
  name: "headerMain",
  data() {
    return {
      links: [
        {
          navLinks: "Home",
          anchors: "Home",
        },
        {
          navLinks: "About us",
          anchors: "About us",
        },
        {
          navLinks: "Service",
          anchors: "Service",
        },
        {
          navLinks: "Price",
          anchors: "Price",
        },
        {
          navLinks: "Contacts",
          anchors: "Contacts",
        },
      ],
    };
  },
  components: {
    LogoHeader,
    NavHeader,
  },
};
</script>

<style scoped>
.header {
  background-color: #edf2ec;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 40px;
  padding-bottom: 30px;
}
</style>
