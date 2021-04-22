<script lang="ts">
export default class TabItem {
  item
  isActive

  constructor(item, isActive = false) {
    this.item = item;
    this.isActive = isActive;
  }

  render() {
    return `
    <div class="tabs__item ${this.isActive ? "tabs--active" : ""}">
      <div class="tabs__title">${this.item.title}</div>

      <div class="tabs__text">${this.item.subtitle}</div>
    </div>
    `;
  }
}
</script>