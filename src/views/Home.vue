<template>
  <div class="home w-full">
    <Top />
    <Nav />
    <Logo class="absolute left-10 w-50 h-50 mt-20 ml-20 z-50" />
    <Slider />
    <ContentSection />
    <ActivitiesPoster />
    <div class="logo mb-14 relative h-40 w-40 mt-10 center mx-auto block"></div>
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
import ActivitiesPoster from "../components/shared/ActivitiesPoster.vue";
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
    ActivitiesPoster,
    ContentSection,
    Logo
  },
};
</script>
