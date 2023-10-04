<template>
    <div class="max-w-screen-xl mx-auto">
      <div id="accordion-collapse" data-accordion="collapse">
        <div v-for="(accordion, index) in accordions" :key="index">
          <div
            class="flex items-center justify-between w-full p-5 font-medium text-left text-gray-600 border border-b-0 border-gray-200 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-800 cursor-pointer"
            @click="toggleAccordion(index)">
            <span class="text-2xl font-bold">{{ accordion.title }}</span>
            <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true"
              xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M9 5 5 1 1 5" />
            </svg>
          </div>
          <transition name="fade">
            <div :key="`accordion-collapse-body-${index}`" v-if="accordion.open"
              class="p-5 border border-b-0 border-gray-200 dark:border-gray-700">
              {{ accordion.content }}
            </div>
          </transition>
        </div>
      </div>
    </div>
</template>
  
<script>
export default {
  data() {
    return {
      accordions: [
        {
          title: "[Day 1] CV And Cover Letter",
          content: "Flowbite is an open-source library...",
          open: false,
        },
        {
          title: "[Day 2] Frontend Learning",
          content: "Flowbite is first conceptualized and designed...",
          open: false,
        },
        {
          title: "[Day 3] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        },
        {
          title: "[Day 4] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        },
        {
          title: "[Day 5] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        },
        {
          title: "[Day 6] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        },
        {
          title: "[Day 7] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        },
        {
          title: "[Day 8] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        }, {
          title: "[Day 9] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        }, {
          title: "[Day 10] Frontend Learning",
          content: "The main difference is that the core components...",
          open: false,
        },
      ],
    };
  },
  methods: {
    toggleAccordion(index) {
      this.accordions[index].open = !this.accordions[index].open;
    },
  },
};
</script>
  
<style scoped>
</style>
  