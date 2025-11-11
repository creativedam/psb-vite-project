<template>
  <div :class="[
    'w-full bg-white h-15 mb-2 md:mb-0 border-b border-sky-800 relative z-50 block transition-all duration-300',
    showMenu ? 'translate-y-0' : '-translate-y-full'
  ]" @mouseleave="closeMenus">


    <!-- Book Button (Mobile) -->
    <router-link
      class="block px-4 py-2 my-2 font-semibold text-base visible sm:hidden text-white shadow-sm absolute pt-2 md:pt-0 top-1 right-4"
      to="/">
      <span class="px-2">+</span> Book Appointment
    </router-link>

    <!-- Main Nav -->
    <div class="md:container md:relative w-full mx-auto block">
      <nav id="menu-main" class="xs:hidden w-full block md:flex justify-center h-15">
        <ul id="nav-main"
          class="xs:hidden md:grid grid-cols-6 h-15 w-3/5 md:w-5/6 text-sky-800 text-base md:text-sm lg:text-base font-medium font-sans">
          <!-- Static Contact Link -->
          <li class="py-4 h-15">
            <router-link class="hover:text-org-100 text-center px-3 border-r border-dashed border-sky-800 block" to="/">
              Home
            </router-link>
          </li>

          <!-- Dynamic Mega Menus -->
          <li v-for="(menu, key) in menus" :key="key" class="py-4 h-15 relative" @mouseenter="activeMenu = key">
            <router-link class="text-center hover:text-org-100 px-4 border-r border-dashed border-sky-800 block"
              :to="menu.url">
              {{ menu.title }}
            </router-link>
          </li>

          <!-- Static Contact Link -->
          <li class="py-4 h-15">
            <router-link class="hover:text-org-100 text-center px-3 border-dashed border-sky-800 block" to="/contacts">
              Contact
            </router-link>
          </li>
        </ul>
      </nav>

      <!-- Dropdown Panels -->
      <div v-for="(menu, key) in menus" :key="key" class="relative" @mouseenter="activeMenu = key"
        @mouseleave="closeMenus">
        <div v-if="activeMenu === key"
          class="grid grid-cols-3 grid-rows-1 h-72 w-full drop-shadow-md z-30 overflow-hidden animate__animated animate__fadeIn">
          <!-- Menu Title -->
          <div class="menu-title h-full py-5 px-8 bg-sky-900/90 text-white">
            <div class="overflow-hidden h-full ml-16">
              <h1 class="text-4xl block text-left font-bold my-6 drop-shadow-md animate__animated animate__fadeInLeft">
                {{ menu.title }}
              </h1>
              <span class="bg-org-200 w-10 h-1 block absolute top-28 left-8"></span>
            </div>
          </div>

          <!-- Menu Items -->
          <div class="level-one bg-white/80 px-8 py-5 text-gray-700">
            <ul class="animate__animated animate__fadeInDown">
              <li v-for="item in menu.items" :key="item.key" class="mb-2 cursor-pointer block w-full">
                <router-link class="py-1 pl-4 block hover:text-org-100 transition hover:border-l-4 border-transparent"
                  :to="item.url" @mouseover="activeTab = item.key">
                  {{ item.label }}
                </router-link>
              </li>
            </ul>
          </div>

          <!-- Tab Content -->
          <div class="level-two bg-white/80 px-8 py-5 text-left text-gray-700">
            <div v-for="item in menu.items" :key="item.key" v-show="activeTab === item.key"
              class="h-full p-3 pointer-events-none animate__animated animate__fadeInDown">
              {{ item.description }}
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

// state
const activeMenu = ref(null)
const activeTab = ref(null)
const showMenu = ref(true)
let lastScrollY = 0

// close all menus
const closeMenus = () => {
  activeMenu.value = null
  activeTab.value = null
}

// scroll hide logic
const handleScroll = () => {
  if (window.scrollY > lastScrollY) {
    showMenu.value = false
    closeMenus()
  } else {
    showMenu.value = true
  }
  lastScrollY = window.scrollY
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

// menu structure
const menus = {
  about: {
    title: 'About',
    url: '/about',
    items: [
      { label: 'Mission', key: 'mission', description: 'This will be our mission', url: '/about' },
      { label: 'Vision', key: 'vision', description: 'This will be our vision', url: '/about' },
      { label: 'Values', key: 'values', description: 'This will be our values', url: '/about' }
    ]
  },
  services: {
    title: 'Membership',
    url: '/',
    items: [
      { label: 'Membership 1', key: '1', description: 'Membership description 1', url: '#' },
      { label: 'Membership 2', key: '2', description: 'Membership description 2', url: '/' },
      { label: 'Membership 3', key: '3', description: 'Membership description 3', url: '#' }
    ]
  },
  activities: {
    title: 'Activities',
    url: '/',
    items: [
      { label: 'Activity 1', key: '1', description: 'Activity description 1', url: '#' },
      { label: 'Activity 2', key: '2', description: 'Activity description 2', url: '/' },
      { label: 'Activity 3', key: '3', description: 'Activity description 3', url: '#' }
    ]
  },
  Gallerys: {
    title: 'Gallery',
    url: '/',
    items: [
      { label: 'Gallery 1', key: '1', description: 'Gallery description 1', url: '#' },
      { label: 'Gallery 2', key: '2', description: 'Gallery description 2', url: '/' },
      { label: 'Gallery 3', key: '3', description: 'Gallery description 3', url: '#' }
    ]
  }
}
</script>

<style>
.translate-y-full {
  transform: translateY(-100%);
}
</style>
