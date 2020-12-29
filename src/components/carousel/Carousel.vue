<template>
  <div class="carousel">
    <slot></slot>
    <button class="carousel__nav prev" @click.prevent="prev"></button>
    <button class="carousel__nav next" @click.prevent="next"></button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      index: 0,
      slides: [],
      direction: "right",
    };
  },
  mounted() {
    this.slides = this.$children;
  },
  computed: {
    slidesCount() {
      return this.slides.length;
    },
  },
  methods: {
    next() {
      this.index++;
      this.direction = "right";
      if (this.index >= this.slidesCount) {
        this.index = 0;
      }
    },
    prev() {
      this.index--;
      this.direction = "left";
      if (this.index < 0) {
        this.index = this.slidesCount - 1;
      }
    },
  },
};
</script>

<style src="./carousel.scss" lang="scss"></style>
