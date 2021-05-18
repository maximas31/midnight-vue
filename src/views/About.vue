<template>
  <div class="about">
    <h1>Cate oua are Vova? {{ something }}</h1>

    <button @click="onClicked">Castrare</button>
    <!-- <router-link :to="{ name: 'about', params: { something: something > 0 ? something - 1 : 0 } }">Castrare</router-link> -->
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class HelloWorld extends Vue {
  public something = 15;

  // get something() {
  //   const something: any = this.$route.params.something;

  //   return parseInt(something);
  // }

  created() {
    console.log(this.something);
  }

  public onClicked() {
    if (this.something > 0) {
      this.something -= 1;
    }
  }
}
</script>
