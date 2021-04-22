<template>
  <nav class="navigation header__navigation">
    <MenuItem v-for="(item, index) in navigationItems" :key="item.id" :item="item" @mouseenter="showDropdownMenu(index)" @mouseleave="hideDropdownMenu(index)">
      <DropdownMenu v-if="hasChildren(item)" :menu-item="item" :is-hidden="getVisibilityByIndex(index).isHidden" :is-faded="getVisibilityByIndex(index).isFaded" />
    </MenuItem>
  </nav>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

import { MenuItem } from "./menu-item";
import { DropdownMenu } from "./dropdown-menu";

@Options({
  name: "Navigation",
  components: {
    MenuItem,
    DropdownMenu,
  }
})
export default class Navigation extends Vue {
  public timer: any = null;

  public dropdownVisibility: any = {};

  public hoveredItem: any = null;

  public get navigationItems() {
    return [
      {
        id: "product",
        name: "Product",
        items: [
          {
            icon: "home.svg",
            title: "Homepage",
            subtitle: "Get to know Midnight Theme"
          }, 
          {
            icon: "faq.svg",
            title: "How It Works",
            subtitle: "Learn how Midnight can help"
          },
          {
            icon: "price.svg",
            title: "Pricing & FAQ",
            subtitle: "Find the right plan for you"
          },
          {
            icon: "contact.svg",
            title: "Contact",
            subtitle: "Get in touch with our team"
          },
        ]
      },
      {
        id: "company",
        name: "Company",
        items: [
          {
            icon: "group.svg",
            title: "About us",
            subtitle: "Get to know our team and mission"
          }, 
          {
            icon: "blog.svg",
            title: "Blog",
            subtitle: "Read our amazing articles"
          }
        ],
        links: [
          {
            text: "Privacy Policy",
            to: "https://google.com"
          },
          {
            text: "Terms of Service",
            to: "https://google.com"
          }
        ]
      },
      {
        id: "blog",
        name: "Blog",
        items: []
      },
      {
        id: "contact",
        name: "Contact",
        items: []
      }
    ]
  }

  public hasChildren(item: { id: string; items: any[]; links?: any[] }): boolean {
    return !!item.items.length;
  }

  public showDropdownMenu(index: number) {
    clearTimeout(this.timer);

    this.dropdownVisibility[index] = {
      isHidden: false,
      isFaded: true
    }
    
    this.timer = setTimeout(() => this.dropdownVisibility[index].isFaded = false, 10);
  }

  public hideDropdownMenu(index: number) {
    this.dropdownVisibility[index] = {
      isHidden: true,
      isFaded: true
    };
  }

  public getVisibilityByIndex(index: number): any {
    return this.dropdownVisibility[index] || {
      isHidden: true,
      isFaded: true
    };
  }
}
</script>

<style lang="scss" scoped>
.navigation {
  display: flex;
  font-size: 15px;
}
</style>
