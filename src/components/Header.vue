<template>
  <header>
    <div class="topbar">
      <a href="#" class="topbar_logo">
        <img src="./../assets/svg/logo.svg" alt="Logo" />
      </a>
      <nav class="topbar_nav">
        <a href="#about" class="active" @click.prevent="scrollTo('about')"
          >about</a
        >
        <a href="#service" @click.prevent="scrollTo('service')">service</a>
        <a href="#works" @click.prevent="scrollTo('works')">works</a>
        <a href="#blog" @click.prevent="scrollTo('blog')">blog</a>
        <a href="#contact" @click.prevent="scrollTo('contact')">contact</a>
      </nav>
      <span class="topbar-social">
        <a href="http://twitter.com" target="_blank">
          <span class="icon icon_twitter"></span>
        </a>
        <a href="http://facebook.com" target="_blank">
          <span class="icon icon_facebook"></span>
        </a>
        <a href="http://linkdin.com" target="_blank">
          <span class="icon icon_linkedin"></span>
        </a>
      </span>
    </div>
    <Carousel>
      <CarouselSlide v-for="(slide, i) in slides" :key="i" :index="i">
        <div class="carousel_text">
          <h1>
            We transform every <br />
            dream into digital <br />
            reality
          </h1>
          <button class="btn_danger">
            Discover
          </button>
        </div>
        <img :src="slide.img" width="100%" :alt="slide.alt" />
      </CarouselSlide>
    </Carousel>
  </header>
</template>

<script>
import Carousel from "./Carousel.vue";
import CarouselSlide from "./CarouselSlide.vue";
export default {
  name: "Header",
  components: {
    Carousel,
    CarouselSlide,
  },
  data() {
    return {
      slides: [
        {
          text: "We transform every /n dream into digital /n reality",
          img: "./assets/img/marvin-meyer-571072-unsplash.png",
          alt: "marvin-meyer-571072-unsplash",
        },
        {
          text: "We transform every dream into digital reality",
          img: "./assets/img/marvin-meyer-571072-unsplash copy1.png",
          alt: "marvin-meyer-571072-unsplash copy1",
        },
        {
          text: "We transform every dream into digital reality",
          img: "./assets/img/marvin-meyer-571072-unsplash copy2.png",
          alt: "marvin-meyer-571072-unsplash copy2",
        },
      ],
    };
  },
  methods: {
    scrollTo(elementId) {
      let el = document.querySelector(`#${elementId}`);
      el.scrollIntoView({
        behavior: "smooth",
        block: "start",
      });
    },
  },
};
</script>

<style lang="scss">
.topbar {
  margin: 0px;
  padding: 0px;
  width: 100%;
  height: 80px;
  display: flex;
  align-items: center;

  a {
    text-decoration: none;
    color: inherit;
  }

  .topbar_logo {
    display: block;
    width: 80px;
    height: 80px;
    margin: 0px;
    padding: 0px;
    img {
      height: 80px;
      width: 80px;
    }
  }

  .topbar_nav {
    font-size: 14px;
    line-height: 20px;
    font-family: Roboto-Regular;
    color: #000000;
  }

  .topbar_nav a {
    margin: 0 60px;
    transition: opacity 0.3s;
    &:hover {
      opacity: 0.7;
    }
  }

  .topbar-social {
    margin-left: auto;
    margin-right: 10px;
  }
}

.icon::after {
  content: "";
  display: inline-block;
  width: 20px;
  height: 20px;
  font-size: 14px;
  margin: 0 5px;
  background-image: url(./../assets/svg/twitter.svg);
}

.icon {
  transition: opacity 0.3s;
  &:hover {
    opacity: 0.7;
  }
}

.icon_twitter::after {
  background-image: url(./../assets/svg/twitter.svg);
}

.icon_facebook::after {
  background-image: url(./../assets/svg/facebook.svg);
}
.icon_facebook::after {
  background-image: url(./../assets/svg/facebook.svg);
}
.icon_linkedin::after {
  background-image: url(./../assets/svg/linkedin.svg);
}
</style>
