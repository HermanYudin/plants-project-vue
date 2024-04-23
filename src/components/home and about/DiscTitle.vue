<template>
  <div class="home-title-container">
    <h1 v-if="about" class="home-title" :class="{ about: about }">
      <span
        v-for="(word, index) in titleAbout.split(' ')"
        :key="index"
        :style="{
          color:
            word === 'professional' || word === 'experienced'
              ? '#E06733'
              : '#499a18',
        }"
        >{{ word }}
      </span>
    </h1>
    <h1 v-else class="home-title">
      <span
        v-for="(word, index) in titleHome.split(' ')"
        :key="index"
        :style="{ color: word === 'plants' ? '#499A18' : 'gray' }"
        >{{ word }}
      </span>
    </h1>
  </div>
</template>

<script>
export default {
  name: "DiscTitleHome",
  props: {
    titleHome: {
      type: String,
    },
    titleAbout: {
      type: String,
    },
    about: {
      type: Boolean,
    },
  },
};
</script>

<style scoped>
.home-title {
  font-size: 45px;
  font-family: "bold";
}
.about {
  font-family: "inika-regular";
  font-size: 40px;
  font-weight: normal;
  max-width: 463px;
  width: 100%;
}
</style>
