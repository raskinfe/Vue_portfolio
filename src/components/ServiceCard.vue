<template>
  <div class="card" v-for="(content, index) in content" :key="index">
    <div :class="classHandler(index)" class="card-items">
      <DefaultImage
        :source="cardImage"
        :width="600"
        :height="400"
        class="card-image"
      ></DefaultImage>
      <div class="card-content">
        <h1 class="title">{{ content.title }}</h1>
        <p class="description">{{ content.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import DefaultImage from "../globalComponents/DefaultImage.vue";

export default {
  name: "ServiceCard",
  components: { DefaultImage },
  props: {
    cardImage: {
      type: String,
    },
    content: {
      type: Object,
    },
  },
  methods: {
    classHandler(index) {
      console.log("called");
      return index > 0 && index % 2 == 1 ? "--inverted" : "";
    },
  },
  mounted() {
    console.log(this.content);
  },
};
</script>

<style lang="scss" scoped>
.card {
  display: flex;
  align-content: center;
  background: #2f3944;
  color: white;
  .card-items {
    display: flex;
    .card-image{
        opacity: .6;
    }
    .card-content {
      width: 600px;
      padding: 20px;
      height: 400px;
      h1 {
        margin-bottom: 20px;
      }
      p {
        font-size: 1rem;
      }
    }
  }
  .--inverted {
    display: grid;
    grid-template-areas: "content img";
    .card-image {
      grid-area: img;
    }
    card-content {
      grid-area: content;
    }
  }
}
</style>
