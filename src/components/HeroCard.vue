<script>
import { store } from "../constants/store.js";
import DefaultImage from "../globalComponents/DefaultImage.vue";
import NavCard from "./NavCard.vue";
export default {
  name: "HeroCard",
  data() {
    return {
      state: store.state,
    };
  },
  components: { DefaultImage, NavCard },
  computed: {
    path() {
      return this.state.heroImage.path;
    },
    fullName() {
      return `${this.state.firstName} ${this.state.lastName}`;
    },
    links() {
      console.log(this.state.links);
      return this.state.links;
    },
  },
};
</script>
<template>
  <div class="hero">
    <NavCard :linkContent="links" :fullName="fullName"></NavCard>
    <DefaultImage
      class="hero-image"
      :source="path"
      :width="100"
      :height="100"
      :hero="true"
    ></DefaultImage>
  </div>
</template>

<style lang="scss">
.hero {
  display: flex;
  margin: 0;
  padding: 0;
  flex-direction: column;
  margin-bottom: 50px;
  .hero-image {
    position: relative;
    top: 0;
    left: 0;
  }

}
</style>
