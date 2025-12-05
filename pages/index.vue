<template>
  <div class="min-h-screen bg-[#0C2554] flex flex-col items-center py-10 px-6">

    <!-- TITLE -->
    <h1 class="text-4xl font-bold text-white text-center mb-4">
      WaterStar Monitoring Portal
    </h1>

    <!-- DESCRIPTION -->
    <p class="text-lg text-white max-w-2xl text-center mb-10">
      This portal provides real-time environmental data of the North Kazakhstan Region. 
      You can explore water levels, lake coordinates, transparency, temperature and other hydrological indicators.
    </p>

    <!-- QUICK LINKS SECTION -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 w-full max-w-4xl">

      <!-- BUTTON: LAKES MAP -->
      <NuxtLink
        to="/Lab3"
        class="bg-[#D0A300] hover:bg-[#0c2554d2] text-white font-semibold py-4 px-6 rounded-xl shadow-md text-center"
      >
        Water levels (Map)
      </NuxtLink>

      <!-- BUTTON: WATER TRANSPARENCY -->
      <NuxtLink
        to="/Lab4"
        class="bg-[#D0A300] hover:bg-[#0c2554d2] text-white font-semibold py-4 px-6 rounded-xl shadow-md text-center"
      >
        Transparency
      </NuxtLink>

      <!-- BUTTON: TEMPERATURE -->
      <NuxtLink
        to="/Lab5"
        class="bg-[#D0A300] hover:bg-[#0c2554d2] text-white font-semibold py-4 px-6 rounded-xl shadow-md text-center"
      >
        Water temperature
      </NuxtLink>

      <!-- BUTTON: ELECTRICAL CONDUCTIVITY -->
      <NuxtLink
        to="/Lab6"
        class="bg-[#D0A300] hover:bg-[#0c2554d2] text-white font-semibold py-4 px-6 rounded-xl shadow-md text-center"
      >
        Electrical conductivity
      </NuxtLink>

      <!-- BUTTON: COORDINATES (YOUR MAP PAGE) -->
      <NuxtLink
        to="/Lab0"
        class="bg-[#D0A300] hover:bg-[#0c2554d2] text-white font-semibold py-4 px-6 rounded-xl shadow-md text-center"
      >
        Coordinates & Lakes
      </NuxtLink>

      <!-- BUTTON: ABOUT PATHOGENS -->
      <NuxtLink
        to="/inform"
        class="bg-[#D0A300] hover:bg-[#0c2554d2] text-white font-semibold py-4 px-6 rounded-xl shadow-md text-center"
      >
        Pathogens information
      </NuxtLink>

    </div>

  </div>
</template>
