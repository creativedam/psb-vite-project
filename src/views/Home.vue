<template>
  <div class="home w-full">
    <Top />
    <Nav />
    <Logo class="absolute left-10 w-50 h-50 mt-20 ml-20 z-50" />
    <Slider />
    <ContentSection />
    <div class="logo mb-14 relative h-40 w-40 center mx-auto block"></div>

    <h1 class="text-skys-800 text-4xl py-5 text-center font-bold">
      Our website is under maintanace
    </h1>
    <h2 class="w-full text-center p-4 text-black text-bold text-2xl">
      Join Today
    </h2>
    <p class="w-full text-center p-4 text-sky-950">
      Reach us on info@psb.org.bw
    </p>

    <p class="w-full text-center p-4 text-sky-950">
      Welcome to Pharmaceutical Society Of Botswana
    </p>
    <Footer />
  </div>
</template>

<script>
import Top from "@/components/Top.vue";
import Nav from "@/components/nav/Nav.vue";
import Footer from "@/components/Shared/Footer.vue";
import Slider from "@/components/Shared/Slider.vue";
import Strip from "@/components/Shared/Strip.vue";
import About from "@/components/Shared/About.vue";
import ContentSection from "@/components/Shared/ContentSection.vue";
import Logo from "@/components/Shared/Logo.vue";

export default {
  name: "Home",
  components: {
    Top,
    Nav,
    Footer,
    Slider,
    Strip,
    About,
    ContentSection,
    Logo
  },
};
</script>
