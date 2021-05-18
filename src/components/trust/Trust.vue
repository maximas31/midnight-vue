<template>
  <section class="trust">
    <div class="container">
      <div class="trust__text">The world's best companies trust Midnight</div>

      <div class="trust__logos">
        <img src="img/logo1.png" alt="logo-1" class="trust__logo" />

        <img src="img/logo2.png" alt="logo-2" class="trust__logo" />

        <img src="img/logo3.png" alt="logo-3" class="trust__logo" />

        <img src="img/logo4.png" alt="logo-4" class="trust__logo" />

        <img src="img/logo5.png" alt="logo-5" class="trust__logo" />

        <img src="img/logo6.png" alt="logo-6" class="trust__logo" />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Trust extends Vue {}
</script>

<style lang="scss" scoped>
.trust {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-bottom: 100px;

  &__text {
    text-align: center;
    font-size: 18px;
    line-height: 1.8;
    color: #57586e;
  }

  &__logos {
    display: flex;
    justify-content: space-between;
    margin-top: 30px;
  }

  &__logo {
    width: 200px;
  }
}
</style>
