<template>
  <footer class="footer">
    <div class="container">
      <GetEmail />

      <hr noshade class="footer__divider">

      <section class="footer__bottom">
        <div>
          <img src="img/logo-footer.jpg" alt="logo-footer" class="footer__logo">

          <div class="footer__credits">Designed and developed by <a href="">Flowyak</a> |<br>Powered by <a
              href="">Webflow</a></div>
          <div class="footer__social-icons">
            <a href="#"><img src="img/facebook.png" alt="facebook" class="footer__social-icon"></a>

            <a href="#"><img src="img/instagram.png" alt="instagram" class="footer__social-icon"></a>

            <a href="#"><img src="img/twitter.png" alt="twitter" class="footer__social-icon"></a>
          </div>
        </div>

        <div v-for="menuSection in menuSections" :key="menuSection[0]">
          <div class="footer__title">{{ menuSection[0] }}</div>

          <a class="footer__link" href="#" v-for="link in menuSection[1]" :key="link">
            {{ link }}
          </a>
        </div>
      </section>
    </div>
  </footer>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

import GetEmail from "./GetEmail.vue";

@Options({
  components: {
    GetEmail
  }
})
export default class Footer extends Vue {
  get menuSections() {
    return [
      ["PRODUCT", ["Home", "How it works", "Pricing & FAQs"]],
      ["RESOURCES", ["Blog", "Contact", "Licensing"]],
      ["COMPANY", ["About us", "Privacy Policy", "Terms of Service"]]
    ]
  }
}
</script>

<style lang="scss" scoped>
.footer {
  padding: 120px 0;
  background-color: #0a083b;
  color: white;

  &__divider {
    color: #1d1b4a;
    background-color: #1d1b4a;
    border: none;
    height: 2px;
  }

  &__bottom {
    padding-top: 20px;
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 1fr;
    grid-template-rows: auto;
    gap: 0px 20px;
  }

  &__logo {
    height: 50px;
    img {
      height: 100%;
    }
  }

  &__credits {
    max-width: 300px;
    margin-top: 20px;
    color: hsla(0, 0%, 100%, 0.7);
    font-size: 14px;
    line-height: 1.7;

    a {
      color: #fff;
      text-decoration: none;
    }
  }

  &__social-icons {
    display: flex;
  }

  &__social-icon {
    width: 30px;
    margin-right: 15px;
    margin-top: 20px;
  }

  &__title {
    margin-bottom: 15px;
    color: #fff;
    font-size: 14px;
    font-weight: 600;
    line-height: 1;
  }

  &__link {
    display: block;
    color: #ffffffb3;
    transition: color 300ms;
    font-size: 14px;
    line-height: 1;
    text-decoration: none;
    margin-bottom: 15px;

    &:hover {
      color: #ffffff;
    }
  }
}
</style>