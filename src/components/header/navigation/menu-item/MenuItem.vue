<template>
  <div class="navigation__item">
    <div>{{ item.name }}</div>

    <div class="navigation__icon" v-if="children.length">
      <img src="img/dropdown-arrow.png" alt="nav-icon" />
    </div>

    <slot />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  name: "MenuItem",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
})
export default class MenuItem extends Vue {
  public item!: { id: string; items: any[]; links?: any[] };

  get children(): any[] {
    return this.item.items || [];
  }
}
</script>

<style lang="scss" scoped>
.navigation {
  &__item {
    position: relative;
    padding: 20px 7px;
    margin: 0 5px;
    color: #57586e;
    display: flex;
    cursor: pointer;
    transition: all 200ms ease;

    &:hover {
      color: #0047f0;

      .navigation__icon {
        transform: rotate(180deg);
        filter: invert(16%) sepia(100%) saturate(3212%) hue-rotate(222deg)
          brightness(99%) contrast(111%);
      }
    }
  }

  &__icon {
    margin-left: 4px;
    padding: 0 3px;
    transition: all 300ms;

    img {
      width: 10px;
    }
  }
}
</style>
