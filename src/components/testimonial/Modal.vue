<template>
  <div class="modal__container" @click.self='closeModal'>
      <div class="modal__content">
        <iframe v-if="showModal"
          width="890"
          height="500"
          src="https://www.youtube-nocookie.com/embed/dQw4w9WgXcQ?autoplay=1&controls=0"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        >
        </iframe>

        <button type="button" class="modal__close" 
          @click='closeModal'> X 
        </button>
      </div>
  </div>

</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  name: "Modal",
  props: {
    showModal: Boolean
  }
})
export default class Modal extends Vue {
  // showModal = false;

  closeModal() {
    this.$emit('closeModal')
  }
}
</script>

<style lang="scss" scoped>
.modal {
  &__container {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6);
  }

  &__content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    

    &:before,
    &:after {
      border-radius: 25px;
      content: "";
      position: absolute;
      left: -2px;
      top: -2px;
      background: linear-gradient(
        45deg,
        #fb0094,
        #0000ff,
        #00ff00,
        #ffff00,
        #ff0000,
        #fb0094,
        #0000ff,
        #00ff00,
        #ffff00,
        #ff0000
      );
      background-size: 400%;
      width: calc(100% + 4px);
      height: calc(100% + 4px);
      z-index: -1;
      animation: steam 20s linear infinite;
    }

    &:after {
      filter: blur(50px);
    }

    iframe {
      border-radius: 25px;
      background: linear-gradient(0deg, #000, #272727);
    }
  }

  @keyframes steam {
    0% {
      background-position: 0 0;
    }
    50% {
      background-position: 400% 0;
    }
    100% {
      background-position: 0 0;
    }
  }

  .block:after {
    filter: blur(50px);
  }

  &__close {
    position: absolute;
    background: linear-gradient(0deg, #000, #272727);
    right: -10%;
    border-radius: 100%;
    font-size: 25px;
    color: black;
    font-weight: bold;
    z-index: 5;
    width: 50px;
    height: 50px;
    cursor: pointer;

    &:before, &:after {
      border-radius: 25px;
      content: "";
      position: absolute;
      left: -2px;
      top: -2px;
      background: linear-gradient(
        45deg,
        #fb0094,
        #0000ff,
        #00ff00,
        #ffff00,
        #ff0000,
        #fb0094,
        #0000ff,
        #00ff00,
        #ffff00,
        #ff0000
      );
      background-size: 400%;
      width: calc(100% + 4px);
      height: calc(100% + 4px);
      z-index: -1;
      animation: steam 20s linear infinite;
    }

    &:after {
      filter: blur(50px);
    }
  }
}
</style>