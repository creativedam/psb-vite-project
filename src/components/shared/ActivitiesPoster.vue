<template>
    <section class="w-full bg-sky-600/10 py-16 font-lusitana">
        <div class="container mx-auto px-4">

            <div class="flex flex-col md:flex-row items-center gap-8">

                <!-- PDF Thumbnail -->
                <div class="w-full md:w-1/2 flex justify-center">
                    <a :href="pdfUrl" target="_blank" rel="noopener">
                        <img :src="poster" alt="Download Rates PDF"
                            class="w-full max-w-md rounded-lg shadow-lg hover:scale-105 transition duration-300" />
                    </a>
                </div>

                <!-- Text + Button -->
                <div class="w-full md:w-1/2 text-center md:text-left">
                    <h2 class="text-3xl font-bold text-sky-800 mb-4">
                        Become a Member
                    </h2>

                    <p class="text-gray-600 mb-6">
                        Join us today
                    </p>

                    <a :href="pdfUrl" target="_blank" rel="noopener"
                        class="bg-sky-500 relative px-4 border  rounded-2xl border-white py-4 my-2 w-60
                         font-semibold text-base text-white hover:text-sky-800 hover:bg-white  hover:border-sky-800 text-center shadow-sm">
                        Join
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"
                            class="w-5 h-5 inline-block">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                        </svg>
                    </a>
                </div>

            </div>

        </div>
    </section>
</template>

<script setup>
const poster = new URL('@/assets/psb_poster.jpg', import.meta.url).href
const pdfUrl = "#"
</script>