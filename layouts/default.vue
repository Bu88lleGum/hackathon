<template>
  <div class="min-h-screen flex flex-col bg-white">

    <header class="z-50 w-full flex items-center justify-between px-6 py-4 bg-[#FAD22C] text-black">

  <!-- LOGO + TEXT -->
  <NuxtLink to="/" class="flex items-center gap-3">
    <img 
      src="/assets/images/logo.svg" 
      alt="logo" 
      class="w-20 h-20 object-contain"
    />
  </NuxtLink>

  <!-- Desktop -->
  <nav class="hidden md:flex gap-6 text-lg">
    <NuxtLink to="/" class="hover:text-[#D0A300] hover:bg-[#0C2554] rounded-lg p-2">Home</NuxtLink>
    <NuxtLink to="/inform" class="hover:text-[#D0A300] hover:bg-[#0C2554] rounded-lg p-2">Pathogens</NuxtLink>
    <NuxtLink to="/Lab3" class="hover:text-[#D0A300] hover:bg-[#0C2554] rounded-lg p-2">Water level</NuxtLink>
    <NuxtLink to="/Lab4" class="hover:text-[#D0A300] hover:bg-[#0C2554] rounded-lg p-2">Transparency</NuxtLink>
    <NuxtLink to="/Lab5" class="hover:text-[#D0A300] hover:bg-[#0C2554] rounded-lg p-2">Temperature</NuxtLink>
    <NuxtLink to="/Lab6" class="hover:text-[#D0A300] hover:bg-[#0C2554] rounded-lg p-2">Electrical conductivity</NuxtLink>
  </nav>

  <!-- Burger button -->
  <button @click="burgerOpen = true" class="flex flex-col gap-1 md:hidden">
    <span class="w-7 h-[3px] bg-black"></span>
    <span class="w-7 h-[3px] bg-black"></span>
    <span class="w-7 h-[3px] bg-black"></span>
  </button>
</header>


    <!-- OVERLAY -->
    <transition name="fade">
      <div
        v-if="burgerOpen"
        class="fixed inset-0 bg-black/40 z-[9998]"
        @click="burgerOpen = false"
      ></div>
    </transition>

    <!-- BURGER SIDEBAR -->
    <transition name="slide">
      <aside
        v-if="burgerOpen"
        class="fixed left-0 top-0 h-full w-64 bg-[#FAD22C] text-white shadow-lg z-[9998] p-6 flex flex-col gap-6"
      >
        <button class="ml-auto text-2xl" @click="burgerOpen = false">✕</button>

    <NuxtLink to="/" class="text-[#D0A300] bg-[#0C2554] rounded-lg p-2"@click="closeBurger">Home</NuxtLink>
    <NuxtLink to="/inform" class="text-[#D0A300] bg-[#0C2554] rounded-lg p-2"@click="closeBurger">Pathogens</NuxtLink>
    <NuxtLink to="/Lab3" class="text-[#D0A300] bg-[#0C2554] rounded-lg p-2"@click="closeBurger">Water level</NuxtLink>
    <NuxtLink to="/Lab4" class="text-[#D0A300] bg-[#0C2554] rounded-lg p-2"@click="closeBurger">Transparency</NuxtLink>
    <NuxtLink to="/Lab5" class="text-[#D0A300] bg-[#0C2554] rounded-lg p-2"@click="closeBurger">Temperature</NuxtLink>
    <NuxtLink to="/Lab6" class="text-[#D0A300] bg-[#0C2554] rounded-lg p-2"@click="closeBurger">Electrical conductivity</NuxtLink>
      </aside>
    </transition>

    <!-- MAIN CONTENT -->
    <main class="flex-1">
      <slot/>
    </main>

    <!-- FOOTER -->
    <footer class="w-full bg-[#FAD22C] text-white py-4 mt-auto flex justify-center gap-6">
      <a href="https://github.com/Bu88lleGum/hackathon"><img src="/assets/images/github.svg" class="w-20 h-20"/></a>
    </footer>

  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const burgerOpen = ref(false)
const closeBurger = () => (burgerOpen.value = false)
</script>

<style>
/* Slide animation */
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.25s ease;
}
.slide-enter-from,
.slide-leave-to {
  transform: translateX(-100%);
}

/* Fade overlay */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
