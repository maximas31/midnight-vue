<template>
  <GlobalAlert />
  <Header />
  <Hero />
  <Trust />
  <About />
  <Testimonial />
  <GetStarted />
  <Footer />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

import GlobalAlert from "@/components/global-alert/GlobalAlert.vue";
import Header from "@/components/header/Header.vue";
import Hero from "@/components/hero/Hero.vue";
import Trust from "@/components/trust/Trust.vue";
import About from "@/components/about/About.vue";
import Testimonial from "@/components/testimonial/Testimonial.vue";
import GetStarted from "@/components/get-started/GetStarted.vue";
import Footer from "@/components/footer/Footer.vue";

@Options({
  components: {
    GlobalAlert,
    Header,
    Hero,
    Trust,
    About,
    Testimonial,
    GetStarted,
    Footer,
  },
})
export default class Home extends Vue {}
</script>
