<template>
  <div class="modal__container" @click="onCloseClicked">
    <div class="modal__content">
      <div class="modal__video">
        <iframe
          width="950"
          height="550"
          src="https://www.youtube-nocookie.com/embed/dQw4w9WgXcQ?autoplay=1&controls=0"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        />
      </div>

      <button type="button" class="modal__close" @click="onCloseClicked">
        X
      </button>
    </div>
    <div class="modal__surprise">
      <img
        v-for="pepe in pepes"
        :key="pepe"
        src="../../../public/img/surprise.gif"
        :alt="pepe"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  name: "Modal",
})
export default class Modal extends Vue {
  public pepes: any[] = [];

  onCloseClicked() {
    this.$emit("close-clicked");
  }

  mounted() {
    for (let pepe = 0; pepe < 300; pepe++) {
      this.pepes.push(pepe);
    }
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
  }

  &__video {
    overflow: hidden;
    width: 680px;
    height: 495px;
    border-radius: 25px;
    background: linear-gradient(0deg, #000, #272727);

    iframe {
      transform: translate(-14%, -8%);
    }
  }

  &__close {
    position: absolute;
    background: linear-gradient(0deg, #000, #272727);
    right: -15%;
    top: 0;
    border-radius: 100%;
    font-size: 25px;
    color: black;
    font-weight: bold;
    z-index: 5;
    width: 50px;
    height: 50px;
    cursor: pointer;

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

  &__surprise {
    display: flex;
    justify-content: space-between;
    flex-flow: row wrap;
    align-items: flex-end;
    height: 140px;
    z-index: -1;

    img {
      height: 80px;
    }
  }
}
</style>
