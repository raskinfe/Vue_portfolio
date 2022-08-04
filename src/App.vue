<script>
import ServiceCard from "./components/ServiceCard.vue";
import HeroCard from "./components/HeroCard.vue";
import { store } from "./constants/store.js";
export default {
  name: "App",
  components: { ServiceCard, HeroCard },
  data() {
    return {
      state: store.state,
    };
  },
  computed: {
    serviceContent() {
      return this.state.contents.services;
    },
    imageSource() {
      return "/src/assets/web-development.webp";
    },
  },
};
</script>
<template>
  <header>
    <hero-card></hero-card>
    <div class="content-container">
      <div class="content-items">
        <div class="services" id="services">
          <div class="title"><h1>Services</h1></div>
          <service-card
            :content="serviceContent"
            :cardImage="imageSource"
          ></service-card>
        </div>
      </div>
    </div>
  </header>
</template>
<style lang="scss" scoped>
.content-container {
  display: flex;
  justify-content: center;
  margin-top: 50px;
  .content-items {
    display: flex;
    flex-direction: column;
    justify-content: center;
    .services {
      display: flex;
      flex-direction: column;
      justify-content: center;
      .title{
        display: flex;
        justify-content: center;
        margin-bottom: 30px;
        h1 {
          font-size: 2.6rem;
        }
      }
    }
  }
}
</style>
