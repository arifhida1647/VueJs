<template>
    <!-- Cauresel -->
    <div class="relative" id="caursel">
        <div class="overflow-hidden  w-full h-64 md:h-96 ">
            <div class="absolute inset-0 flex items-center justify-center w-full h-full">
                <div class="w-full h-full bg-cover bg-center bg-no-repeat"
                    :style="{ backgroundImage: 'url(' + images[currentIndex] + ')' }"></div>
                <div class="absolute inset-0 flex items-center justify-center">
                    <div class="text-center py-20 bg-cover bg-center bg-no-repeat" id="head">
                        <h1 class="mb-4 text-4xl font-extrabold tracking-tight 0 md:text-5xl text-white">
                            Arif Learning Path
                        </h1>
                        <p class="mb-6 text-lg font-normal text-white lg:text-xl">
                            Here at Flowbite we focus on markets where technology, innovation, and capital can unlock
                            long-term value and
                            drive economic growth.
                        </p>
                        <a href="#"
                            class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 dark:focus:ring-blue-900">
                            Learn more
                            <svg class="w-3.5 h-3.5 ml-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 14 10">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M1 5h12m0 0L9 1m4 4L9 9" />
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
        <div class="absolute inset-x-0 bottom-60 md:bottom-60 p-4">
            <div class="flex items-center justify-between">
                <button @click="prev" class="bg-white text-gray-800 p-2 rounded-full focus:outline-none">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                        xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                    </svg>
                </button>
                <button @click="next" class="bg-white text-gray-800 p-2 rounded-full focus:outline-none">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                        xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                    </svg>
                </button>
            </div>
        </div>
    </div>
    <!-- Course -->
    <div class="max-w-screen-xl mx-auto">
        <div class="text-center py-20 bg-cover bg-center bg-no-repeat" id="head">
            <h1
                class="mb-4 text-xl font-bold tracking-tight md:text-2xl text-gray-800 dark:text-white border-b-2 border-orange-600 inline-block  pb-3">
                Available Course
            </h1>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
            <div v-for="(item, index) in items" :key="index">
                <div
                    class="h-auto max-w-full bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
                    <a :href="item.link">
                        <img class="rounded-t-lg" :src="item.imageSrc" alt="" />
                    </a>
                    <div class="p-5">
                        <a :href="item.link">
                            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
                                {{ item.title }}
                            </h5>
                        </a>
                        <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{{ item.description }}</p>
                        <a :href="item.link"
                            class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                            Read more
                            <svg class="w-3.5 h-3.5 ml-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 14 10">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M1 5h12m0 0L9 1m4 4L9 9" />
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!-- Gallery -->
    <div class="bg-gray-200 mt-20 dark:bg-slate-800">
        <div class="max-w-screen-xl mx-auto">
            <div class="text-center py-20 bg-cover bg-center bg-no-repeat" id="head">
                <h1
                    class="mb-20  text-xl font-bold tracking-tight md:text-2xl text-gray-800 dark:text-white border-b-2 border-orange-600 inline-block  pb-3">
                    Gallery
                </h1>
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                    <div v-for="(column, columnIndex) in imageGrid" :key="columnIndex" class="grid gap-4">
                        <div v-for="(item, itemIndex) in column" :key="itemIndex">
                            <img class="h-auto max-w-full rounded-lg" :src="item.src" alt="Gambar">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!-- contact -->
    <div class="max-w-screen-xl mx-auto py-20">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
            <div class="md:mx-auto text-center">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                    stroke="currentColor" class="w-12 h-12 mb-6 mx-auto dark:text-white">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z" />
                    <path stroke-linecap="round" stroke-linejoin="round"
                        d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z" />
                </svg>
                <h1 class="dark:text-white">
                    Tangerang Selatan, Indonesia
                </h1>
            </div>
            <div class="md:mx-auto text-center">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                    stroke="currentColor" class="w-12 h-12 mb-6 mx-auto dark:text-white">
                    <path stroke-linecap="round" stroke-linejoin="round"
                        d="M10.5 1.5H8.25A2.25 2.25 0 006 3.75v16.5a2.25 2.25 0 002.25 2.25h7.5A2.25 2.25 0 0018 20.25V3.75a2.25 2.25 0 00-2.25-2.25H13.5m-3 0V3h3V1.5m-3 0h3m-3 18.75h3" />
                </svg>

                <h1 class="dark:text-white">
                    +62 856 9509 1825
                </h1>
            </div>
            <div class="md:mx-auto text-center">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                    stroke="currentColor" class="w-12 h-12 mb-6 mx-auto dark:text-white">
                    <path stroke-linecap="round" stroke-linejoin="round"
                        d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75" />
                </svg>

                <h1 class="dark:text-white">
                    arifhida1647@gmail.com
                </h1>
            </div>
        </div>
    </div>

    <!-- footer -->
    <div class="dark:border-gray-800 border-t-2 dark:bg-black">
        <div class="max-w-screen-xl mx-auto pt-10 pb-10 ">
            <div class="grid grid-cols-1  md:grid-cols-2 md:gap-x-60">
                <div class="justify-start">
                    <div class="dark:text-white">ALL @ RESERVED INSEE</div>
                </div>
                <div class="justify-end flex">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-8 h-8 mr-5 dark:text-white">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M8.625 12a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H8.25m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H12m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0h-.375M21 12c0 4.556-4.03 8.25-9 8.25a9.764 9.764 0 01-2.555-.337A5.972 5.972 0 015.41 20.97a5.969 5.969 0 01-.474-.065 4.48 4.48 0 00.978-2.025c.09-.457-.133-.901-.467-1.226C3.93 16.178 3 14.189 3 12c0-4.556 4.03-8.25 9-8.25s9 3.694 9 8.25z" />
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-8 h-8 mr-5 dark:text-white">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75" />
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-8 h-8 mr-5 dark:text-white">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M10.5 1.5H8.25A2.25 2.25 0 006 3.75v16.5a2.25 2.25 0 002.25 2.25h7.5A2.25 2.25 0 0018 20.25V3.75a2.25 2.25 0 00-2.25-2.25H13.5m-3 0V3h3V1.5m-3 0h3m-3 18.75h3" />
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-8 h-8 mr-5 dark:text-white">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z" />
                    </svg>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            currentIndex: 0,
            items: [
                {
                    imageSrc: 'https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80',
                    title: "Noteworthy technology acquisitions 2021",
                    description: "Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.",
                    link: "#",
                },
                {
                    imageSrc: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    title: "Noteworthy technology acquisitions 2021",
                    description: "Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.",
                    link: "#",
                },
                {
                    imageSrc: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    title: "Noteworthy technology acquisitions 2021",
                    description: "Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.",
                    link: "#",
                },
                {
                    imageSrc: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    title: "Noteworthy technology acquisitions 2021",
                    description: "Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.",
                    link: "#",
                },
                {
                    imageSrc: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    title: "Noteworthy technology acquisitions 2021",
                    description: "Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.",
                    link: "#",
                },
                {
                    imageSrc: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    title: "Noteworthy technology acquisitions 2021",
                    description: "Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.",
                    link: "#",
                },
                // Tambahkan item lainnya sesuai kebutuhan Anda.
            ],
            imageGrid: [
                [
                    {
                        src: "https://images.unsplash.com/photo-1543002588-bfa74002ed7e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    },
                    {
                        src: "https://images.unsplash.com/photo-1532012197267-da84d127e765?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    },
                ],
                [
                    {
                        src: "https://images.unsplash.com/photo-1541963463532-d68292c34b19?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1976&q=80",
                    },
                    {
                        src: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80",
                    },
                    {
                        src: "https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image-5.jpg",
                    },
                ],
                [
                    {
                        src: "https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image-6.jpg",
                    },
                    {
                        src: "https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image-7.jpg",
                    },
                    {
                        src: "https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image-8.jpg",
                    },
                ],
                [
                    {
                        src: "https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image-9.jpg",
                    },
                    {
                        src: "https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image-10.jpg",
                    },
                    {
                        src: "https://flowbite.s3.amazonaws.com/docs/gallery/masonry/image-11.jpg",
                    },
                ],
            ],
            images: [
                'https://images.unsplash.com/photo-1695418624980-1b26cb42b58a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1682686581220-689c34afb6ef?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1695751240451-2e499d93eb6c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1695650858277-6d1eb7ce3216?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1696299872422-0f72e707a037?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
            ],
        };
    },
    methods: {
        next() {
            // Delay the image change to allow the transition effect to be visible
            setTimeout(() => {
                this.currentIndex = (this.currentIndex + 1) % this.images.length;
            }, 100); // You can adjust the delay as needed
        },
        prev() {
            // Delay the image change to allow the transition effect to be visible
            setTimeout(() => {
                this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
            }, 100); // You can adjust the delay as needed
        },
    },
};
</script>
<style scoped>
#caursel {
    height: 900px;
}

#caursel .bg-cover {
    transition: background-image 0.3s ease-in-out;
}
</style>