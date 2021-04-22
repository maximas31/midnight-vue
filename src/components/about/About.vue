<template>
  <section class="about">
    <div class="container">
      <div class="about__one tabs"></div>

      <div class="about__parallax-container">
        <div class="about__two">
          <div class="about__image">
            <img
              src="icons/gray-background.svg"
              alt="gray-background"
              class="about__background-img-1"
              data-parallax="1.9"
            />

            <img
              src="icons/blue-background.svg"
              alt="blue-background"
              class="about__background-img-2"
              data-parallax="2.5"
            />

            <img
              src="icons/Image_1.svg"
              alt="image-1"
              class="about__primary-img-1"
              data-parallax="-4"
            />
          </div>

          <div class="about__content">
            <h3>High-converting, high-performing.</h3>

            <ul>
              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>Convert traffic into quality leads and sales</div>
              </li>

              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>The fastest loading speed</div>
              </li>

              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>Integrates with all your favorite tools</div>
              </li>

              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>100% money back guarantee</div>
              </li>
            </ul>

            <button class="button about__button">BUY NOW</button>

            <hr />

            <div class="about__testimonial-small">
              <img
                src="img/small_logo3.png"
                alt="small-logo3"
                class="about__testimonial-small-logo"
              />

              <div class="about__testimonial-small-text">
                “Midnight was our first template. It was without doubt the main
                factor to our success." <br /><br /><span>Philip Wink,</span>
                CEO & Founder
              </div>
            </div>
          </div>
        </div>

        <div class="about__three">
          <div class="about__content">
            <h3>Impress your visitors with a clean interface.</h3>

            <ul>
              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>Modern and polished layouts</div>
              </li>

              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>Carefully selected, open source fonts</div>
              </li>

              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>Mobile responsive</div>
              </li>

              <li>
                <img src="img/checkmark.png" alt="checkmark" />
                <div>Done-for-you setup and custom assets</div>
              </li>
            </ul>

            <button class="button about__button">BUY NOW</button>

            <hr />

            <div class="about__testimonial-small">
              <img
                src="img/small_logo2.png"
                alt="small-logo2"
                class="about__testimonial-small-logo"
              />

              <div class="about__testimonial-small-text">
                “Midnight is the template all startups need. High-converting,
                fast, and beautiful”. <br /><br /><span>Eric Tunner,</span> CEO
                & Founder
              </div>
            </div>
          </div>

          <div class="about__image">
            <img
              src="icons/Image_2.svg"
              alt="image-2"
              class="about__primary-img-2"
              data-parallax="-4"
            />

            <img
              src="icons/gray-background.svg"
              alt="gray-background"
              class="about__background-img-3"
              data-parallax="3"
            />

            <img
              src="icons/blue-background.svg"
              alt="blue-background"
              class="about__background-img-4"
              data-parallax="2"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.about {
  padding-top: 90px;

  &__one {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    padding: 120px 0;
    display: flex;
    justify-content: space-between;
    width: 100%;
    .about__content {
      max-width: 44%;
    }
  }

  &__content {
    max-width: 480px;
    padding-top: 23px;
    padding-bottom: 44px;
    hr {
      margin-top: 25px;
      size: 1px;
      opacity: .4;
      color: rgba(153, 153, 153, 0);
    }
  }

  &__headings {
    max-width: 480px;
    margin-bottom: 56px;
  }

  &__heading {
    font-size: 40px;
    font-weight: 600;
    color: #0a083b;
    line-height: 1.2;
  }

  &__subheading {
    font-size: 18px;
    color: #57586e;
    line-height: 1.5;
    margin-top: 10px;
  }

  &__image {
    display: flex;
    justify-content: center;
    width: 56%;
    position: relative;
  }

  &__tabs {
    padding-bottom: 10px;
  }

  &__two {
    overflow: hidden;
    padding: 80px 0;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    width: 100%;
  }

  ul {
    margin-top: 25px;
  }

  li {
    display: flex;
    margin-bottom: 20px;
    align-items: flex-end;
    img {
      width: 15px;
      margin-top: 7px;
      margin-right: 8px;
    }

    div {
      color: #57586e;
      font-size: 16px;
    }
  }

  &__primary-img-1 {
    position: absolute;
    width: 367px;
    z-index: 1;
    top: 510px;
    left: 195px;
  }

  &__background-img-1 {
    position: absolute;
    width: 350px;
    top: -1470px;
    right: 12px;
  }

  &__background-img-2 {
    position: absolute;
    width: 350px;
    left: 40px;
    top: -1050px;
  }

  &__testimonial-small {
    display: flex;
    margin-top: 20px;
    align-items: flex-start;
  }
  
  &__testimonial-small-logo {
    max-width: 110px;
    margin-top: 5px;
  }
  
  &__testimonial-small-text {
    margin-left: 20px;
    color: #57586e;
    font-size: 15px;
    line-height: 1.7;
    font-weight: 400;

    span {
      font-weight: 600;
    }
  }

  &__three {
    overflow: hidden;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    padding: 80px 0;
    width: 100%;
  }

  &__primary-img-2 {
    position: absolute;
    width: 367px;
    z-index: 1;
    top: 720px;
    right: 193px;
  }
  
  &__background-img-3 {
    position: absolute;
    width: 350px;
    top: -1220px;
    right: -40px;
  }
  
  &__background-img-4 {
    position: absolute;
    width: 350px;
    right: 60px;
    top: -1800px;
  }

  &__button {
    margin-top: 10px;
  }
}
</style>

<script lang="ts">
import { Vue } from "vue-class-component";
// import Tabs from "./tabs/Tabs.vue";
// import Parallax from "./parallax/Parallax.vue";

export default class About extends Vue {

  // render() {
  //   this.initChild();
  // }

  // initChild() {
  //     const tabs = new Tabs('.tabs');
  //     const parallax = new Parallax('.about__parallax-container');

  //     tabs.render();
  //     tabs.init();
  //     parallax.init();
  // }
}
</script>