<template>
  <div class="tabs">
    <div class="tabs__content">
      <div class="tabs__headings">
        <h3 class="tabs__heading">Midnight can help you</h3>

        <div class="tabs__subheading">
          Midnight cuts the time and cost it takes to build an effective and
          beautiful website.
        </div>
      </div>

      <div class="tabs__tabs" ref="container">
        <TabItem
          v-for="(tabItem, index) in tabItems"
          :key="tabItem.title"
          :item="tabItem"
          @click="
            activateTab(index);
            isSlideshowEnabled = false;
          "
          @mouseover="pauseSlideshow"
          @mouseleave="startSlideshow"
        />
      </div>

      <button class="button tabs__button">BUY THIS TEMPLATE</button>
    </div>

    <div class="tabs__image">
      <Transition name="fade" mode="out-in">
        <img
          :key="activeTabIndex"
          :src="`img/${tabItems[activeTabIndex].image.name}`"
          :alt="`${tabItems[activeTabIndex].image.alt}`"
          class="tabs__image"
        />
      </Transition>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import TabItem from "./TabItem.vue";

@Options({
  name: "Tabs",
  components: {
    TabItem,
  },
})
export default class Tabs extends Vue {
  public activeTabIndex = 0;
  public tabTimer: number | undefined;
  public isSlideshowEnabled = false;

  public tabItems: any[] = [
    {
      title: "Get your project running. Fast.",
      subtitle:
        "Just add your content to our professionally designed templates and you are ready to go.",
      image: {
        name: "Iphone_1-p-500.png",
        alt: "phone-1",
      },
      isActive: true,
    },
    {
      title: "Professional design, affordable price.",
      subtitle:
        "We have been designing high-converting websites and helping startups grow since 2015. Get all the benefits for a tiny cost.",
      image: {
        name: "Iphone_2-p-500.png",
        alt: "phone-2",
      },
      isActive: false,
    },
    {
      title: "All-around amazing performance.",
      subtitle:
        "Great design is your first impression, the foundation of your brand. See the results in your bottom line.",
      image: {
        name: "Iphone_3-p-500.png",
        alt: "phone-3",
      },
      isActive: false,
    },
    {
      title: "Easy to use and customize.",
      subtitle:
        "Webflow's no-code editor is as easy as a doc and offers great tutorials for all your needs.",
      image: {
        name: "Iphone_4-p-500.png",
        alt: "phone-4",
      },
      isActive: false,
    },
  ];

  public get tabsContainer(): Element | null {
    return (this.$refs.container as Element) || null;
  }

  mounted() {
    this.observeTabsOnViewport();
  }

  public observeTabsOnViewport() {
    if (!this.tabsContainer) {
      return;
    }

    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            this.isSlideshowEnabled = true;
            this.startSlideshow();
          }

          if (!entry.isIntersecting) {
            this.pauseSlideshow();
            this.isSlideshowEnabled = false;
          }
        });
      },
      {
        threshold: 0,
      }
    );

    observer.observe(this.tabsContainer);
  }

  public activateTab(index = 0) {
    this.tabItems[this.activeTabIndex].isActive = false;

    this.activeTabIndex = index;

    this.tabItems[this.activeTabIndex].isActive = true;
  }

  public startSlideshow() {
    if (!this.isSlideshowEnabled) {
      return;
    }

    this.tabTimer = setInterval(() => {
      let index = this.activeTabIndex + 1;

      if (index >= this.tabItems.length) {
        index = 0;
      }

      this.activateTab(index);
    }, 1000);
  }

  public pauseSlideshow() {
    if (!this.isSlideshowEnabled) {
      return;
    }

    clearInterval(this.tabTimer);
  }
}
</script>

<style lang="scss" scoped>
.tabs {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  padding: 120px 0;
  display: flex;
  justify-content: space-between;
  width: 100%;

  .tabs__content {
    max-width: 44%;
  }

  &__content {
    max-width: 480px;
    padding-top: 23px;
    padding-bottom: 44px;
    hr {
      margin-top: 25px;
      size: 1px;
      opacity: 0.4;
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
    padding-bottom: 30px;
  }
}

.fade {
  &-enter-active {
    transition: opacity 450ms ease-in;
  }
  &-leave-active {
    transition: opacity 150ms ease-in;
  }
  &-enter-from,
  &-leave-to {
    opacity: 0;
  }
}
</style>
