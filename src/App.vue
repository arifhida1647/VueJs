<script setup>
import List from './components/listCourse.vue'
import Heading from './components/headingCourse.vue'
import Sidebar from './components/sidebar.vue'
import ListUser from './components/listUserCourse.vue'
import HomePage from './components/HomePage.vue'
import AboutPage from './components/aboutPage.vue'
import ContactPage from './components/contactPage.vue'
import { ref, reactive } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
AOS.init({
      // Pengaturan AOS di sini
      duration: 800, // Durasi animasi dalam milidetik
      easing: 'ease-in-out', // Gaya animasi
    });
// Fungsi untuk mengganti tema
let isDarkMode = false;
const toggleTheme = () => {
  isDarkMode = !isDarkMode;
  if (isDarkMode) {
    document.body.classList.add('dark');
  } else {
    document.body.classList.remove('dark');
  }
}
const state = reactive({
  activeTab: 'profile',
});

const setActiveTab = (tab) => {
  isDarkMode = false,
    state.activeTab = tab;
};

const stateNav = reactive({
  activeNav: 'Home',
});

const setActiveNav = (nav) => {
  isDarkMode = false,
    stateNav.activeNav = nav;
};

// tombol untuk navbar
document.addEventListener('DOMContentLoaded', function () {
  const button = document.querySelector('[data-collapse-toggle="navbar-default"]');
  const menu = document.getElementById('navbar-default');

  button.addEventListener('click', function () {
    const expanded = menu.getAttribute('aria-expanded');

    if (expanded === 'true') {
      menu.style.display = 'none';
      menu.setAttribute('aria-expanded', 'false');
    } else {
      menu.style.display = 'block';
      menu.setAttribute('aria-expanded', 'true');
    }
  });
});

// fungsi untuk navbar ganti pages

</script>

<template>
  <div :class="{ 'dark': isDarkMode }">

    <div class="dark:bg-gray-900">
      <!-- navbar -->
      <nav class="bg-white dark:border-t-blue-700 border-t-4 border-orange-400 dark:bg-gray-900 fixed top-0 w-full z-10">
        <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
          <a class="flex items-center">
            <span class="self-center text-3xl font-mono font-semibold whitespace-nowrap dark:text-white">Arif</span>
          </a>
          <button data-collapse-toggle="navbar-default" type="button"
            class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
            aria-controls="navbar-default" aria-expanded="false">
            <span class="sr-only">Open main menu</span>
            <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M1 1h15M1 7h15M1 13h15" />
            </svg>
          </button>
          <div class="hidden w-full md:block md:w-auto" id="navbar-default">
            <ul
              class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
              <li>
                <a @click="setActiveNav('Home')" :class="{
                  'block py-2 pl-3 pr-4 text-gray-900  bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 dark:text-white md:dark:text-blue-500': stateNav.activeNav === 'Home',
                  'block py-2 pl-3 pr-4 text-gray-900 rounded cur hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent': stateNav.activeNav !== 'Home',
                }" aria-current="page" class="cursor-pointer">Home</a>
              </li>
              <li>
                <a @click="setActiveNav('Course')" :class="{
                  'block py-2 pl-3 pr-4 text-gray-900  bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 dark:text-white md:dark:text-blue-500': stateNav.activeNav === 'Course',
                  'block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent': stateNav.activeNav !== 'Course',
                }" aria-current="page" class="cursor-pointer">Course</a>
              </li>
              <li>
                <a @click="setActiveNav('About')" :class="{
                  'block py-2 pl-3 pr-4 text-gray-900  bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 dark:text-white md:dark:text-blue-500': stateNav.activeNav === 'About',
                  'block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent': stateNav.activeNav !== 'About',
                }" aria-current="page" class="cursor-pointer">About</a>
              </li>
              <li>
                <a @click="setActiveNav('Contact')" :class="{
                  'block py-2 pl-3 pr-4 text-gray-900  bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 dark:text-white md:dark:text-blue-500': stateNav.activeNav === 'Contact',
                  'block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent': stateNav.activeNav !== 'Contact',
                }" aria-current="page" class="cursor-pointer">Contact</a>
              </li>
              <li>
                <div class="py-5 md:py-0 pl-3 pr-4">
                  <label class="relative inline-flex items-center cursor-pointer ">
                    <input type="checkbox" value="" class="sr-only peer" @change="toggleTheme">
                    <div
                      class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-blue-300 dark:peer-focus:ring-blue-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-blue-600">
                    </div>
                    <span class="ml-3 text-sm font-medium text-gray-900 dark:text-gray-300">Dark Mode</span>
                  </label>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </nav>
      <!-- Sidebar -->
      <Sidebar class="fixed hidden md:block z-10" />
      
      <!-- Page Home -->
      <div v-if="stateNav.activeNav === 'Home'">
        <HomePage />
      </div>
       <!-- About -->
       <div v-if="stateNav.activeNav === 'About'">
        <AboutPage/>
      </div>
      <!-- page course -->
      <div v-if="stateNav.activeNav === 'Course'">
        <!-- Heading -->
        <Heading />
        <!-- NAV LINK -->
        <div class="max-w-screen-xl mx-auto pb-5">
          <div class="text-sm font-medium text-center text-gray-500 dark:text-gray-400 dark:border-gray-700">
            <ul
              class="flex flex-wrap text-sm font-medium text-center text-gray-500 border-b border-gray-200 dark:border-gray-700 dark:text-gray-400">
              <li class="mr-2">
                <h1 @click="setActiveTab('profile')" :class="{
                  'border-b-2 border-transparent': state.activeTab !== 'profile',
                  'inline-block p-4 text-blue-600 border-b-2 border-blue-600 rounded-t-lg active dark:text-blue-500 dark:border-blue-500': state.activeTab === 'profile',
                }"
                  class="inline-block p-4 rounded-t-lg hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300 cursor-pointer">
                  Dashboard
                </h1>
              </li>
              <li class="mr-2">
                <h1 @click="setActiveTab('dashboard')" :class="{
                  'border-b-2 border-transparent': state.activeTab !== 'dashboard',
                  'inline-block p-4 text-blue-600 border-b-2 border-blue-600 rounded-t-lg active dark:text-blue-500 dark:border-blue-500': state.activeTab === 'dashboard',
                }"
                  class="inline-block p-4 rounded-t-lg hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300 cursor-pointer">
                  User
                </h1>
              </li>
            </ul>
          </div>
        </div>

        <div  v-if="state.activeTab === 'profile'" class="dark:bg-gray-900" >
          <List/>
        </div>
        <div v-if="state.activeTab === 'dashboard'">
          <ListUser />
        </div>
      
      </div>
     
      <!-- Contact -->
      <div v-if="stateNav.activeNav === 'Contact'">
      <ContactPage />  
    </div>
    </div>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}


.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
