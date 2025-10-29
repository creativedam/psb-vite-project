<template>
    <div class="about w-full">
        <Top />
        <Nav />
        <h1 class=" text-sky-800 text-4xl py-5 text-center font-bold">About</h1>
        <p class="w-full text-center p-4 text-black">
            We are Pharmaceutical Society Of Botswana
        </p>
        <p class="w-full text-center p-4 text-sky-950">
            Reach us on info@psb.org.bw
        </p>
        <Footer />
    </div>
</template>

<script>
import Top from '@/components/Top.vue'
import Nav from '../components/nav/Nav.vue';
import Footer from '../components/Shared/Footer.vue';

export default {
    name: 'Home',
    components: {
        Top,
        Nav,
        Footer
    }
}


</script>