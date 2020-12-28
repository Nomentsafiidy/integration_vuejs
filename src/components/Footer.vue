<template>
  <footer class="footer">
    <div class="footer_top">
      <h4>
        Say hello
      </h4>
    </div>
    <article class="footer_center">
      <section class="footer_left">
        <div class="footer_tab ">
          <div class="tab">
            <a
              href="#"
              :class="{ active: tabActive == 'paris' }"
              @click.prevent="changeTabTo('paris')"
              >PARIS</a
            >
          </div>
          <div class="tab">
            <a
              href="#"
              :class="{ active: tabActive == 'london' }"
              @click.prevent="changeTabTo('london')"
              >LONDON</a
            >
          </div>
        </div>
        <div class="footer_tab_content">
          <p v-for="(content, i) in tabContent.contents" :key="i">
            {{ content }}
          </p>
        </div>
        <div class="footer_social_media">
          <div>FOLLOW US</div>
          <a href="http://twitter.com" target="_blank">
            <span class="icon icon_twitter"></span>
          </a>
          <a href="http://facebook.com" target="_blank">
            <span class="icon icon_facebook"></span>
          </a>
          <a href="http://linkdin.com" target="_blank">
            <span class="icon icon_linkedin"></span>
          </a>
        </div>
      </section>
      <section class="footer_right">
        <form action="">
          <div class="form_group">
            <label for="name" class="float_label">Name *</label>
            <input class="footer_input" type="text" name="name" />
          </div>
          <div class="form_group">
            <label for="email" class="float_label">Email *</label>
            <input class="footer_input" type="email" name="email" />
          </div>
          <div class="form_group">
            <label for="message" class="float_label">Message *</label>
            <textarea class="footer_textarea" rows="4"></textarea>
          </div>
          <div class="content_center">
            <button class="btn btn_dark">Send</button>
          </div>
        </form>
      </section>
    </article>
    <article class="footer_bottom">
      <div>Copyright © Tous droits réservés 2018</div>
      <div>
        <a href="#" class="margin_left">Conditions générales de vente</a>
        <a href="#" class="margin_left">Politique de confidentialité </a>
        <a href="#" class="margin_left"> Mentions légales</a>
      </div>
    </article>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      tabs: [
        {
          name: "paris",
          contents: {
            location: "1 rue de Paris - 75009 Paris",
            number: "+33 9 34 67 89 45",
          },
        },
        {
          name: "london",
          contents: {
            location: "16 rue de london - 7509 london",
            number: "+261 9 34 67 89 45",
          },
        },
      ],
      tabContent: {
        name: "paris",
        contents: {
          location: "1 rue de Paris - 75009 Paris",
          number: "+33 9 34 67 89 45",
        },
      },
    };
  },
  methods: {
    changeTabTo(tabName) {
      this.tabs.forEach((tab) => {
        if (tabName === tab.name) {
          this.tabContent = tab;
        }
      });
    },
  },
  computed: {
    tabActive() {
      return this.tabContent.name;
    },
  },
};
</script>

<style lang="scss">
a {
  color: inherit;
  text-decoration: none;
}
.margin_left {
  margin-left: 10px;
}
.footer_bottom {
  font-family: Montserrat-Light;
  font-size: 14px;
  line-height: 19px;
  background: #ea4235;
  color: #ffffff;
  display: flex;
  height: 48px;
  align-items: center;
  justify-content: space-evenly;
}
.footer {
  background: #323232;
  color: #ffffff;
  .footer_top {
    padding: 25px 0;
    text-align: center;
    font-family: Montserrat-Medium;
    font-size: 36px;
    line-height: 48px;
  }
}
.footer_center {
  display: flex;
  padding: 0 140px 60px;
  .footer_left {
    display: flex;
    flex-direction: column;
    width: 40%;
  }
  .footer_right {
    width: 60%;
  }
}
.footer_tab {
  display: flex;
  .tab {
    color: #b1b1b1;
    padding-right: 15px;
    margin-right: 15px;
    font-family: Montserrat-Light;
    font-size: 28px;
    line-height: 37px;
  }
  .active {
    color: #ffffff;
  }

  .active::after {
    content: "";
    display: block;
    border: solid 1px #ffffff;
    width: calc(100% + 15px);
  }
}
.footer_tab_content {
  font-family: Montserrat-Light;
  font-size: 28px;
  line-height: 37px;
}

.footer_social_media {
  font-family: Montserrat-Regular;
  font-size: 26px;
  font-weight: 400;
  line-height: 35px;
}

.footer_right {
  color: #ffffff;
  font-family: "Montserrat-Light";
  font-size: 20px;
  line-height: 27px;
}

.btn_dark {
  padding: 0 35px;
  color: #ffffff;
  border: solid 1px white;
  background: transparent;
  font-family: "Montserrat-Bold";
  font-size: 22px;
  line-height: 29px;
}
.footer_input {
  background: transparent;
  height: 42px;
  border: none;
  border-bottom: solid 1px #ffffff;
  width: 100%;
}
.form_group {
  margin-bottom: 25px;
}
.footer_textarea {
  background: transparent;
  border: none;
  border-bottom: solid 1px #ffffff;
  width: 100%;
}
.content_center {
  text-align: center;
}
.float_label {
  float: left;
  position: absolute;
}
</style>
