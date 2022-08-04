<template>
  <div :style="cssHandler" class="img" :class="[hero ? '--hero' : '']"></div>
</template>
<script>
export default {
  name: "DefaultImage",
  props: {
    source: {
      type: String,
    },
    width: {
      tyoe: Number,
    },
    height: {
      type: Number,
    },
    hero: {
      type: Boolean,
    },
  },
  data() {
    return {};
  },
  computed: {
    cssHandler() {
      if (this.hero) {
        return {
          "--width": this.width + "vw",
          "--height": this.height + "vh",
          "--url": `url(${this.source})`,
        };
      }
      return {
        "--width": this.width + "px",
        "--height": this.height + "px",
        "--url": `url(${this.source})`,
      };
    },
  },
  mounted() {
    console.log(this.cssHandler);
  },
};
</script>

<style lang="scss">
.img {
  width: var(--width);
  height: var(--height);
  display: block;
  background-image: var(--url);
  background-size: cover;
}
.--hero {
  &::after {
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #000;
    opacity: 0.7;
    z-index: -1;
    display: block;
    content: "";
  }
}
</style>
