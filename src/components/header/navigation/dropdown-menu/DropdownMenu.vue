<template>
  <div class="dropdown-menu" :class="rootClasses">
    <div class="dropdown-menu__square"></div>

    <div class="dropdown-menu__content">
      <div class="dropdown-menu__items-container">
        <div v-for="(child, index) in children" :key="child.icon" :class="`dropdown-menu__item dropdown-menu__item-${index + 1}`">
          <div class="dropdown-menu__icon">
            <img :src="`icons/${child.icon}`" :alt="child.title">
          </div>

          <div class="dropdown-menu__text">
            <div class="dropdown-menu__title">{{ child.title }}</div>
              
            <div class="dropdown-menu__subtitle">{{ child.subtitle }}</div>
          </div>
        </div>
      </div>

      <div class="dropdown-menu__links-container" v-if="links.length">
        <a target="_blank" v-for="link in links" :key="link.text" :href="link.to">{{ link.text }}</a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    menuItem: {
      type: Object,
      required: true
    },
    isHidden: Boolean,
    isFaded: Boolean
  }
})
export default class DropdownMenu extends Vue {
  public menuItem!: { id: string; items: any[]; links?: any[] };
  public isHidden!: boolean;
  public isFaded!: boolean;
  

  public get id(): string {
    return this.menuItem.id;
  }

  public get children(): any[] {
    return this.menuItem.items || [];
  }

  public get links(): any[] {
    return this.menuItem.links || [];
  }

  public get animationClass(): string {
    return "dropdown-menu__animation";
  }

  public get rootClasses(): any {
    return {
      'display-none': this.isHidden,
      'dropdown-menu__animation': this.isFaded
    };
  }
}
</script>

<style lang="scss" scoped>
.dropdown-menu {
  position: absolute;
  top: 50px;
  opacity: 1;
  left: -120px;
  background-color: white;
  transition: all 200ms ease-out;

  &:hover {
    opacity: 1;
    display: block;
    transform: translate3d(0px, 0px, 0px) scale3d(1, 1, 1);
  }

  &__animation {
    opacity: 0;
    transform: translate3d(0px, 15px, 0px) scale3d(0.9, 0.9, 1);
  }

  &__square {
    position: relative;
    width: 20px;
    height: 20px;
    top: 13px;
    left: 45%;
    transform: rotate(-45deg);
    background-color: white;
  }

  &__content {
    border-radius: 10px;
    box-shadow: 4px -19px 35px 0 rgba(32, 53, 90, 0.08), 11px 11px 30px -10px rgba(32, 53, 90, 0.15);
  }

  &__item {
    position: relative;
    display: flex;
    align-items: center;
    box-sizing: content-box;
    width: 330px;
    height: 52px;
    padding: 20px;
    cursor: pointer;
    border-radius: 10px;
    background-color: white;
    transition: transform 200ms ease, box-shadow 200ms ease;

    &:hover {
      transform: scale(1.05);
      box-shadow: 7px 15px 45px 2px rgba(123, 136, 168, 0.2);
      opacity: 0.9;
    }
  }

  &__item-1 {
    z-index: 40;
  }

  &__item-2 {
    z-index: 30;
  }

  &__item-3 {
    z-index: 20;
  }

  &__item-4 {
    z-index: 10;
  } 

  &__icon {
    width: 52px;
    height: 52px;
    padding: 14px;
    background-color: #F2F2F2;
    border-radius: 10px;
    img {
      width: 100%;
    }
  }

  &__text {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 5px 20px;
    height: 100%;
  }

  &__title   {
    margin-bottom: 2px;
    color: #0a083b;
    font-size: 15px;
  }

  &__subtitle {
    color: #57586e;
    font-size: 14px;
    padding-bottom: 3px;
  }

  &__second {
    left: -20px;
  }

  &__links-container {
    padding: 20px;
    background-color: #fafafa;
    border-top: 1px solid rgba(0, 0, 0, 0.08);
    a {
      text-decoration: none;
      display: block;
      font-size: 14px;
      padding-bottom: 5px;
      line-height: 1.7;
      cursor: pointer;
      color: #283338;
      &:hover {
        color: #0047f0;
      }
    }
  }
}
</style>
