<template>
  <section class="hero">
    <div class="container">
      <h1 class="hero__title">
        Midnight is a high-converting template for startups.
      </h1>

      <div class="hero__subtitle">
        Kickstart your next project and grow your revenue with this
        high-performing, beautifully crafted template.
      </div>

      <div class="hero__buttons">
        <button class="button">BUY THIS TEMPLATE</button>

        <button class="button button--secondary">LEARN MORE</button>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero {
  padding-top: 60px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  min-height: 640px;
  background-image: url("../../../public/icons/hero_decor-dots.svg"),
    url("../../../public/icons/hero_decor-rows.svg");
  background-position: 100% 57%, 0% 87%;
  background-size: 160px, 270px;
  background-repeat: no-repeat, no-repeat;

  &__title {
    font-size: 72px;
    color: #0a083b;
    font-weight: 600;
    margin-bottom: 30px;
    line-height: 1.1;
  }

  &__subtitle {
    font-size: 20px;
    color: #57586e;
    max-width: 700px;
    margin: 0 auto;
    line-height: 1.7;
  }

  &__buttons {
    display: flex;
    justify-content: space-between;
    margin: 40px auto 0 auto;
    max-width: 430px;
  }
}
</style>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Hero extends Vue {
  // rootNode
  // constructor(rootSelector) {
  //   this.rootNode = document.querySelector(rootSelector);
  // }
  // render() {
  //   const html = `
  //   <div class="container">
  //     <h1 class="hero__title">Midnight is a high-converting template for startups.</h1>
  //     <div class="hero__subtitle">
  //       Kickstart your next project and grow your revenue with this high-performing,
  //       beautifully crafted template.
  //     </div>
  //     <div class="hero__buttons">
  //     <button class="button">BUY THIS TEMPLATE</button>
  //     <button class="button button--secondary">LEARN MORE</button>
  //     </div>
  //   </div>`;
  //   this.rootNode.innerHTML = html;
  // }
}
</script>
