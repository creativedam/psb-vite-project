<template>
    <div class="about w-fu">
        <Top />
        <Nav />
        <h1 class=" text-sky-800 text-4xl py-5 text-center font-bold">Contacts</h1>

        <p class="w-full text-center p-4 text-sky-950 text-2xl">
            We are Pharmaceutical Society Of Botswana
        </p>
        <h2 class="w-full text-center p-4 text-red-500">Our website is under maintanace</h2>
        <p class="w-full text-center p-4 text-sky-950">
            Reach us on : pharmasocietybots2022@gmail.com
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