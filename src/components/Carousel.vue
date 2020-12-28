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

<style lang="scss">
.carousel__nav {
  position: absolute;
  width: 20px;
  height: 39px;
  top: 50%;
  padding: 0;
  border: none;
  cursor: pointer;
}

.carousel__nav.prev {
  background: url(./../assets/svg/prev.svg);
  right: auto;
  left: 100px;
}

.carousel__nav.next {
  background: url(./../assets/svg/next.svg);
  right: 100px;
  left: auto;
}

.carousel {
  display: flex;
  position: relative;
  overflow: hidden;

  .carousel_text {
    position: absolute;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    left: 150px;
    text-align: left;
    color: #fff;
    font-family: Montserrat-Bold;
  }

  .carousel_text h1 {
    font-size: 56px;
    line-height: 60px;
  }
  %btn {
    font-family: Montserrat-Bold;
    font-size: 22px;
    line-height: 29px;
    background: gray;
    color: #fff;
    transition: opacity 0.3s;
    border: none;
    padding: 0px 25px;
    border-radius: 25px;
    height: 51px;
    &:hover {
      background: lighten(gray, 4);
    }
  }
  .btn_danger {
    margin-right: auto;
    @extend %btn;
    font-family: Montserrat-Bold;
    background: #d43d40;
    &:hover {
      background: lighten(#d43d40, 4);
      color: darken(#fff, 4);
    }
  }
}
</style>
