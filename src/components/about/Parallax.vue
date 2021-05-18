<template>
  <div ref="container">
    <slot />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  name: "Parallax",
})
export default class Parallax extends Vue {
  public parallaxImages: any[] = [];

  public get parallaxContainer(): Element | null {
    return (this.$refs.container as Element) || null;
  }

  public mounted() {
    this.getAllParallaxImages();
    this.observeElementOnViewport();
  }

  public observeElementOnViewport() {
    if (!this.parallaxContainer) {
      return;
    }

    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) =>
          this.toggleScrollEvent(entry.isIntersecting)
        );
      },
      {
        threshold: 0,
      }
    );

    observer.observe(this.parallaxContainer);
  }

  public toggleScrollEvent(shouldScroll: any) {
    if (shouldScroll) {
      window.addEventListener("scroll", this.changeImagePosition);
    } else {
      window.removeEventListener("scroll", this.changeImagePosition);
    }
  }

  public changeImagePosition = () => {
    this.parallaxImages.forEach((image) => {
      let imgPos = window.pageYOffset / image[1] + "px";
      image[0].style.cssText = `transform: translateY(${imgPos});`;
    });
  };

  public getAllParallaxImages() {
    if (!this.parallaxContainer) {
      return;
    }

    this.parallaxContainer
      .querySelectorAll("[data-parallax]")
      .forEach((parallaxNode: any) => {
        this.parallaxImages.push([
          document.querySelector(`.${parallaxNode.className}`),
          Number(parallaxNode.getAttribute("data-parallax")),
        ]);
      });
  }
}
</script>
