<template>
    <div class="global-alert">
      <div class="global-alert__container">
        <div class="global-alert__title">NEW</div>
        
        <div class="global-alert__text">Use this space to display important messages.</div>
        
        <div class="global-alert__close">x</div>
      </div>
    </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class GlobalAlert extends Vue {
  public rootNode: Element | null = null;
  
  public closeButtonNode: Element | null = null;

  get hiddenClass() {
    return 'global-alert--hidden';
  }

  get closeButtonClass() {
    return 'global-alert__close';
  }

  mounted() {
    this.rootNode = document.querySelector(".global-alert");
    this.closeButtonNode = document.querySelector(`.${this.closeButtonClass}`);

    this.init()
  }

  init() {
    if (!this.closeButtonNode) {
      return;
    }

    this.closeButtonNode.addEventListener('click', () => this.hide());
  }

  hide() {
    if (!this.rootNode) {
      return;
    }

    this.rootNode.classList.add(this.hiddenClass);
  }
}
</script>

<style scoped lang="scss">
.global-alert {
  width: 100%;
  background-color: #0A083B;
  color: white;
  text-align: center;
  height: 50px;

  &--hidden {
    animation: hide-global-alert .4s 1 ease-in-out; 
    animation-fill-mode: forwards;
  }

  &__container {
    display: flex;
    align-items: center;
    max-width: 1140px;
    height: 100%;
    margin: 0 auto;
  }

  &__title {
    margin-left: auto;
    font-size: 14px;
    margin-right: 15px;
    padding: 6px 12px;
    border-radius: 25px;
    background-color: #175cff;
    line-height: 1;
    font-weight: 600;
  }

  &__text {
    font-weight: 600;
  }

  &__close {
    margin-left: auto;
    line-height: 22px;
    color: #1d1d1f;
    font-weight: 600;
    border-radius: 100%;
    background-color: #fff;
    cursor: pointer;
    width: 25px;
    height: 25px;
  }
}

@keyframes hide-global-alert {
  from {
    margin-top: 0;
  }

  to {
    margin-top: -50px;
  }
}
</style>
