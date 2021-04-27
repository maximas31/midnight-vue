<template>
  <section class="get-started">
    <div class="container">
      <div class="get-started__wrapper">
        <div class="get-started__content">
          <h2 class="get-started__title">Get Started</h2>
          <div class="get-started__text">Kickstart your next project and grow your revenue with this high-converting,
            beautifully crafted template.</div>
          <button class="button">BUY THIS TEMPLATE</button>
        </div>
        <div class="get-started__image">
          <img src="img/cta-image-p-800.png" alt="cta-image">
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class GetStarted extends Vue {}
</script>

<style lang="scss" scoped>
.get-started {
  padding: 120px 0;

  &__wrapper {
    border-radius: 10px;
    background-color: #f1f1f1;
    padding: 80px 50px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__content {
    max-width: 40%;
  }

  &__title {
    color: #0a083b;
    font-size: 48px;
    font-weight: 600;
  }

  &__text {
    margin-top: 20px;
    margin-bottom: 40px;
    color: #57586e;
    font-size: 18px;
    line-height: 1.7;
  }

  &__image {
    padding-left: 20px;
    max-width: 55%;

    img {
      width: 100%;
    }
  }
}
</style>