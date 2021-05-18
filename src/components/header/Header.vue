<template>
  <section class="header">
    <div class="container">
      <div class="header__wrapper">
        <div class="header__logo">
          <a href="#"><img src="img/logo-white.jpg" alt="logo-white" /></a>
        </div>

        <Navigation />

        <button class="button button--small header__button">BUY NOW</button>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Navigation from "./navigation/Navigation.vue";

@Options({
  components: {
    Navigation,
  },
})
export default class Header extends Vue {}
</script>

<style lang="scss" scoped>
.header {
  &__wrapper {
    height: 105px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 20px 0;
  }

  &__logo {
    height: 50px;
    img {
      height: 100%;
    }
  }

  &__navigation {
    margin-left: 47px;
  }

  &__button {
    margin-left: auto;
  }
}
</style>
