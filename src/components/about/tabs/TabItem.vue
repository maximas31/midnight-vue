<template>
  <div :class="`tabs__item ${item.isActive ? 'tabs--active' : ''}`">
    <div class="tabs__title">{{ item.title }}</div>

    <div class="tabs__text">{{ item.subtitle }}</div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  name: "TabItem",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
})
export default class TabItem extends Vue {}
</script>

<style lang="scss">
.tabs {
  &__item {
    padding: 8px 30px 8px 20px;
    border-left-style: solid;
    border-left-color: rgb(221, 221, 221);
    border-left-width: 5px;
    opacity: 0.6;
    transition: opacity 300ms ease-out;
    cursor: pointer;
  }

  &:hover {
    opacity: 1;
  }

  &--active {
    border-left-color: #0047f0;
    opacity: 1;
  }

  &__title {
    margin-bottom: 5px;
    color: #0a083b;
    font-size: 20px;
    line-height: 1.2;
    font-weight: 600;
  }

  &__text {
    color: #57586e;
    font-size: 16px;
    line-height: 1.5;
    font-weight: 400;
  }

  &__image {
    max-height: 780px;
  }
}
</style>
