<template>
  <section class="testimonial">
    <div class="container">
      <div class="testimonial__wrapper">
        <div class="testimonial__video" @click="showModal = true">
          <img
            src="icons/play-icon.svg"
            alt="play-icon"
            class="testimonial__play-button"
          />

          <img
            src="img/Testimonial_image-p-1080.jpeg"
            alt="testimonial-cover"
            class="testimonial__video-image"
          />
        </div>
        <div class="testimonial__content">
          <div class="testimonial__text">
            "The best money I have spent in my life. I saw a 1200% increase in
            my conversion rates and doubled my revenue in just three hours”.
          </div>
          <div class="testimonial__author-wrapper">
            <div class="testimonial__author">
              <span>No One Ever</span><br />CEO & Founder
            </div>
            <div class="testimonial__logo">
              <img src="img/small_logo1.png" alt="small-logo1"/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <Modal v-show="showModal" :show-modal="showModal" @closeModal="onClose" />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Modal from "./Modal.vue";

@Options({
  name: "Testimonial",
  components: {
    Modal
  }
})
export default class Testimonial extends Vue {
  public showModal = false;

  onClose() {
    this.showModal = false;
  }
}
</script>

<style lang="scss" scoped>
.testimonial {
  padding: 120px 0;

  &__wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__video {
    position: relative;
    display: flex;
    max-width: 627px;
    border-radius: 10px;
    overflow: hidden;
    cursor: pointer;

    &:hover .testimonial__play-button {
      transform: scale(1.05);
      opacity: 0.9;
    }
  }

  &__play-button {
    position: absolute;
    width: 95px;
    margin: auto;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    opacity: 0.8;
    transition: all 0.5s ease-in-out;
  }

  &__video-image {
    width: 100%;
  }

  &__text {
    max-width: 513px;
    margin-bottom: 35px;
    color: #57586e;
    font-size: 26px;
    line-height: 1.7;
  }

  &__author-wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__author {
    color: #57586e;
    font-size: 17px;
    line-height: 1.5;

    span {
      font-weight: 600;
      font-size: 18px;
      color: #0a083b;
    }
  }

  &__logo {
    max-width: 110px;
    margin-top: 5px;

    img {
      width: 100%;
    }
  }
}
</style>