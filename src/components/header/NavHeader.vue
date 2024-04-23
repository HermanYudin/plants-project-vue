<template>
  <nav class="menu">
    <ul class="menu-list">
      <li v-for="(link, index) in links" :key="index" class="menu-list-item">
        <a
          class="menu-link"
          :href="`#${link.anchors}`"
          :class="{ orange: link.anchors === 'Home' ? '#e06733' : '' }"
          >{{ link.navLinks }}</a
        >
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "NavHeader",
  props: {
    links: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style scoped>
.menu {
  padding-right: 111px;
}

.menu-list {
  display: flex;
  list-style-type: none;
}

.menu-link {
  color: black;
  text-decoration: none;
  font-family: "inika-regular";
  font-size: 16px;
  transition: all;
  transition-duration: 1s;
}

.orange {
  color: #e06733;
  transition: all;
  transition-duration: 1s;
  font-family: "inika-bold";
  font-size: 16px;
}

.menu-list-item:nth-child(n + 2) {
  margin-left: 46px;
}

.menu-list-item:nth-child(2) {
  min-width: 68px;
}

.menu-link:hover {
  color: #499a18;
}

.menuLinkFirst:hover {
  color: black;
}
</style>
