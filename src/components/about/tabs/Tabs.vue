<template>
  <div></div>
</template>

<style lang="scss" scoped>
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
    opacity: 1;
    transition: opacity 450ms ease-in;

    &--base {
      opacity: 0;
      transition: opacity 150ms ease-in;
    }
  }
}
</style>

<script lang="ts">
import TabItem from "./tab-item/TabItem.vue";

export default class Tabs {
  rootNode
  tabNodes

  activeTabIndex = 0

  constructor(rootSelector) {
    this.rootNode = document.querySelector(rootSelector);
  }

  get tabClass() {
    return "tabs__item";
  }

  get imageClass() {
    return "tabs__image";
  }

  get baseClass() {
    return "tabs__image--base";
  }

  get activationClass() {
    return "tabs--active";
  }

  get activeTab() {
    return this.tabItems[this.activeTabIndex];
  }

  get tabItems() {
    return [
      {
        title: "Get your project running. Fast.",
        subtitle: "Just add your content to our professionally designed templates and you are ready to go.",
        image: {
          name: "Iphone_1-p-500.png",
          alt: "phone-1"
        }
      },
      {
        title: "Professional design, affordable price.",
        subtitle: "We have been designing high-converting websites and helping startups grow since 2015. Get all the benefits for a tiny cost.",
        image: {
          name: "Iphone_2-p-500.png",
          alt: "phone-2"
        }
      },
      {
        title: "All-around amazing performance.",
        subtitle: "Great design is your first impression, the foundation of your brand. See the results in your bottom line.",
        image: {
          name: "Iphone_3-p-500.png",
          alt: "phone-3"
        }
      },
      {
        title: "Easy to use and customize.",
        subtitle: "Webflow's no-code editor is as easy as a doc and offers great tutorials for all your needs.",
        image: {
          name: "Iphone_4-p-500.png",
          alt: "phone-4"
        }
      }
    ]
  }

  init() {
    this.tabNodes = document.querySelectorAll(`.${this.tabClass}`);

    this.setupTabListeners();
  }

  render() {
     this.rootNode.innerHTML = `
      <div class="about__content">
        <div class="about__headings">
          <h3 class="about__heading">Midnight can help you</h3>

          <div class="about__subheading">Midnight cuts the time and cost it takes to build an
            effective and beautiful website.</div>
        </div>

        <div class="about__tabs">
          ${this.renderTabItems()}
        </div>

        <button class="button about__button">BUY THIS TEMPLATE</button>
      </div>

      <div class="about__image">
        ${this.renderTabImage()}
      </div>
     `;
  }

  renderTabItems() {
    return this.tabItems.map((item, index) => new TabItem(item, index === this.activeTabIndex).render()).join("");
  }

  renderTabImage() {
    return `
    <img src="img/${this.activeTab.image.name}" alt="${this.activeTab.image.alt}" class="tabs__image tabs__image--hidden">
    `
  }

  setupTabListeners() {
    this.tabNodes.forEach((tabNode, index) => {
      tabNode.addEventListener('click', () => this.onTabClicked(index));
    });
  }

  onTabClicked(tabIndex) {
    this.activeTabIndex = tabIndex;

    this.render();
    this.init();
  }
}

</script>