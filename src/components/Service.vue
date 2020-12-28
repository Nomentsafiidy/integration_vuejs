<template>
  <article class="service">
    <h3 class="service_title">Our Services</h3>
    <div class="service_body">
      <section class="service_item">
        <img width="149" height="85" src="./../assets/svg/laptop.svg" alt="" />
        <h6>LOREM ISPUM</h6>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Est delectus
          rerum distinctio molestiae accusamus reprehenderit praesentium
        </p>
      </section>
      <section class="service_item">
        <img width="149" height="85" src="./../assets/svg/cog.svg" alt="" />
        <h6>LOREM ISPUM</h6>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Est delectus
          rerum distinctio molestiae accusamus reprehenderit praesentium
        </p>
      </section>
      <section class="service_item">
        <img width="149" height="85" src="./../assets/svg/chart.svg" alt="" />
        <h6>LOREM ISPUM</h6>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Est delectus
          rerum distinctio molestiae accusamus reprehenderit praesentium
        </p>
      </section>
      <section class="service_item">
        <img width="149" height="85" src="./../assets/svg/paint.svg" alt="" />
        <h6>LOREM ISPUM</h6>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Est delectus
          rerum distinctio molestiae accusamus reprehenderit praesentium
        </p>
      </section>
    </div>
  </article>
</template>

<script>
export default {};
</script>

<style lang="scss">
.service {
  display: block;
  padding: 60px;
  color: #404040;
  font-family: Montserrat-Medium;

  .service_title {
    margin: 0px 0px;
    margin-bottom: 60px;
    display: block;
    text-align: center;
    font-size: 36px;
    line-height: 48px;
  }
}
.service_body {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  .service_item {
    width: 267px;
    padding: 0 7px;
    text-align: center;
    img {
      width: auto;
    }
  }
  h6 {
    font-size: 22px;
    line-height: 29px;
    margin: 15px;
  }
  p {
    font-family: Roboto-Regular;
    font-size: 16px;
    line-height: 21px;
  }
}
</style>
