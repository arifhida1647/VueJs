<script>
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
    mounted() {
        AOS.init({
            // Pengaturan AOS di sini
            duration: 800, // Durasi animasi dalam milidetik
            easing: 'ease-in-out', // Gaya animasi
        });
    },
}
</script>
<template lang="">
<div class="max-w-screen-xl mx-auto pt-20">
    <div class="text-center py-20 bg-cover bg-center bg-no-repeat" id="head">
        <h1 data-aos="zoom-in" class="mb-4 text-4xl font-extrabold tracking-tight 0 md:text-5xl text-white">
            Arif Learning Path
        </h1>
        <p data-aos="zoom-in" class="mb-6 text-lg font-normal text-white lg:text-xl">
            Here at Flowbite we focus on markets where technology, innovation, and capital can unlock long-term value and
            drive economic growth.
        </p>
        <a data-aos="zoom-in" href="#" class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 dark:focus:ring-blue-900">
            Learn more
            <svg class="w-3.5 h-3.5 ml-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9" />
            </svg>
        </a>
    </div>
    
</div>
</template>

<style scoped>
#head{
    background-image: url(../assets/unsplash.jpg);
}
</style>
