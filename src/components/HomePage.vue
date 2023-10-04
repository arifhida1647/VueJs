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
    height: 700px;
}

#caursel .bg-cover {
    transition: background-image 0.3s ease-in-out;
}
</style>