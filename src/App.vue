<template>
  <div id="app">
    <div>
      <Header></Header>
      <About id="about"></About>
      <Service id="service"></Service>
      <Work id="works"></Work>
      <Footer id="contact"></Footer>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import About from "./components/About.vue";
import Service from "./components/Service.vue";
import Work from "./components/Work.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: { Header, About, Service, Work, Footer },
};
</script>

<style lang="scss">
@import url("./assets/css/app.scss");
@import url("./assets/css/font.scss");
div {
  font-family: Roboto;
}
</style>
