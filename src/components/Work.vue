<template>
  <article>
    <div class="work">
      <section
        v-for="(work, i) in works"
        :key="i"
        class="work-item"
        @click="showModal(i)"
      >
        <img :src="work.imgSrc" :alt="work.imgAlt" />
        <div class="work_mask"></div>
        <div class="work-item-label">
          <span class="work-title">{{ work.title }}</span>
          <p>{{ work.subTitle }}</p>
        </div>
      </section>
    </div>
    <section class="work_subtitle">
      ALL OUR WORKS
    </section>
    <transition>
      <div v-if="isModalShow" class="work-modal">
        <div class="work_modal_content">
          <span class="close_modal" @click="hideModal">&#10006;</span>
          <div class="modal_title">{{ modalContent.title }}</div>
          <div class="modal_subtitle">{{ modalContent.subTitle }}</div>
          <div class="modal_body">
            <section class="section_right">
              <img :src="modalContent.imgSrc" :alt="modalContent.alt" />
            </section>
            <section class="section_left">
              <h5>{{ modalContent.textTitle }}</h5>
              <div class="section_left_body">
                <p>
                  {{ modalContent.text }}
                </p>
              </div>
              <button class="btn btn_white " @click="hideModal">Lorem</button>
              <button class="btn btn_danger margin-left" @click="hideModal">
                Cuncat
              </button>
            </section>
          </div>
        </div>
      </div>
    </transition>
  </article>
</template>

<script>
export default {
  data() {
    return {
      works: [
        {
          imgSrc: "./assets/img/marc-mueller-654355-unsplash.png",
          imgAlt: "marc-mueller-654355-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force. Let’s say you own a
                department store. The advertising manager of the store is like
                the managing editor of a daily newspaper with his group of
                reporters regularly bringing fresh matter to his desk and the
                different department heads acts as the reporters. Take it on a
                Thursday or Friday, when the big Sunday advertisements are in
                process of construction, the scene is remarkably lively, and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
        {
          imgSrc: "./assets/img/marc-mueller-654355-unsplash.png",
          imgAlt: "marc-mueller-654355-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force. Let’s say you own a
                department store. The advertising manager of the store is like
                the managing editor of a daily newspaper with his group of
                reporters regularly bringing fresh matter to his desk and the
                different department heads acts as the reporters. Take it on a
                Thursday or Friday, when the big Sunday advertisements are in
                process of construction, the scene is remarkably lively, and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
        {
          imgSrc: "./assets/img/marc-mueller-654355-unsplash.png",
          imgAlt: "marc-mueller-654355-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force. Let’s say you own a
                department store. The advertising manager of the store is like
                the managing editor of a daily newspaper with his group of
                reporters regularly bringing fresh matter to his desk and the
                different department heads acts as the reporters. Take it on a
                Thursday or Friday, when the big Sunday advertisements are in
                process of construction, the scene is remarkably lively, and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
        {
          imgSrc: "./assets/img/marc-mueller-654355-unsplash.png",
          imgAlt: "marc-mueller-654355-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force. Let’s say you own a
                department store. The advertising manager of the store is like
                the managing editor of a daily newspaper with his group of
                reporters regularly bringing fresh matter to his desk and the
                different department heads acts as the reporters. Take it on a
                Thursday or Friday, when the big Sunday advertisements are in
                process of construction, the scene is remarkably lively, and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
        {
          imgSrc: "./assets/img/marc-mueller-654355-unsplash.png",
          imgAlt: "marc-mueller-654355-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force. Let’s say you own a
                department store. The advertising manager of the store is like
                the managing editor of a daily newspaper with his group of
                reporters regularly bringing fresh matter to his desk and the
                different department heads acts as the reporters. Take it on a
                Thursday or Friday, when the big Sunday advertisements are in
                process of construction, the scene is remarkably lively, and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
        {
          imgSrc: "./assets/img/marc-mueller-654355-unsplash.png",
          imgAlt: "marc-mueller-654355-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force. Let’s say you own a
                department store. The advertising manager of the store is like
                the managing editor of a daily newspaper with his group of
                reporters regularly bringing fresh matter to his desk and the
                different department heads acts as the reporters. Take it on a
                Thursday or Friday, when the big Sunday advertisements are in
                process of construction, the scene is remarkably lively, and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
        {
          imgSrc: "./assets/img/marc-mueller-654355-unsplash.png",
          imgAlt: "marc-mueller-654355-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force. Let’s say you own a
                department store. The advertising manager of the store is like
                the managing editor of a daily newspaper with his group of
                reporters regularly bringing fresh matter to his desk and the
                different department heads acts as the reporters. Take it on a
                Thursday or Friday, when the big Sunday advertisements are in
                process of construction, the scene is remarkably lively, and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
        {
          imgSrc: "./assets/img/igor-ovsyannykov-329196-unsplash.png",
          imgAlt: "igor-ovsyannykov-329196-unsplash",
          title: "Lorem ipsum",
          subTitle: "Lorem ipsum dolor, sit amet",
          textTitle: "Businesses often become known",
          text: `Today through effective marketing. The marketing may be in the
                form of a regular news item or half column society news in the
                Sunday newspaper. The marketing may be in the form of a heart to
                heart talk with Mr. Brown on his prominent local television
                show. These are all advertising. Businesses cannot get away from
                the force of advertising. If they want to make their products
                known in the marketplace they have to use some form of
                advertisement. Advertising is being more and more known as a
                reasonable and desirable business force.  and the
                man at the head of the advertising department has plenty
                occasions to exercise his ready cleverness and level-headedness.`,
        },
      ],
      isModalShow: false,
      modalContent: null,
    };
  },
  methods: {
    hideModal() {
      this.isModalShow = false;
    },
    showModal(index) {
      this.isModalShow = true;
      this.modalContent = this.works[index];
    },
  },
};
</script>

<style lang="scss">
.btn {
  border: none;
  margin: 0;
  padding: 0;
  font-family: Montserrat-Bold;
  font-size: 22px;
  line-height: 29px;
  height: 51px;
  background: #fff;
  border: solid 1px #d43d40;
  border-radius: 51px;
  padding: 0px 25px;
}

.margin-left {
  margin-left: 10px;
}

.btn_danger {
  color: white;
  background: #d43d40;
  transition: color 0.5s;
  &:hover {
    background: darken(#d43d40, 6);
    color: darken(#ffff, 6);
  }
}

.work {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.work_subtitle {
  display: block;
  padding: 25px;
  text-align: center;
  font-family: Montserrat-Medium;
  font-size: 16px;
  color: #ea4235;
  line-height: 21px;
}
.work-item {
  position: relative;
  width: 360px;
  height: 360px;
  color: #fff;
  cursor: pointer;
  img {
    z-index: 1;
  }
  .work-item-label {
    position: absolute;
    top: 0px;
    z-index: 3;
  }
  .work_mask {
    width: 360px;
    height: 360px;
    position: absolute;
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
    z-index: 2;
    background: linear-gradient(0deg, #fff, #1f1f1f);
    opacity: 0.6;
  }
}
.work-item-label {
  position: absolute;
  top: 0px;
  padding: 30px;
  z-index: 2;
  .work-title {
    font-family: Montserrat-Medium;
    font-size: 18px;
    line-height: 24px;
  }
  p {
    font-family: Roboto-Regular;
    font-size: 14px;
    line-height: 19px;
  }
}
.work-modal {
  z-index: 2001;
  position: fixed;
  top: 0px;
  left: 0px;
  bottom: 0px;
  right: 0px;
  padding: 20px;
  background: rgba(0, 0, 0, 0.5);
}

.work_modal_content {
  position: relative;
  display: block;
  width: 100%;
  height: 100%;
  background: #fff;
  padding: 60px;
  .modal_title {
    font-family: Montserrat-Medium;
    font-size: 32px;
    line-height: 43px;
    color: #000000;
    margin-bottom: 5px;
  }
  .modal_subtitle {
    font-family: Roboto-Regular;
    font-size: 22px;
    line-height: 29px;
    color: #000000;
    margin-bottom: 15px;
  }
  .close_modal {
    position: absolute;
    top: 55px;
    right: 55px;
    padding: 5px;
    color: #000;
    cursor: pointer;
    &:hover {
      color: lighten(#000, 4);
    }
  }
}
.modal_body {
  display: flex;
  position: relative;
  height: calc(100% - 80px);
  .section_right {
    img {
      width: auto;
      height: 100%;
    }
    max-width: 740px;
    max-height: 740px;
    height: 100%;
    margin: 0px;
  }
  .section_left {
    min-width: 40%;
    padding: 0px 20px;
    font-family: Roboto-Regular;
    h5 {
      margin: 0;
      color: #323232;
      font-size: 28px;
      line-height: 37px;
    }
    .section_left_body {
      max-height: calc(100% - 150px);
      overflow-y: auto;
      margin: 20px 0;
    }
    p {
      color: #000000;
      font-size: 18px;
      line-height: 24px;
    }
  }
}
</style>
