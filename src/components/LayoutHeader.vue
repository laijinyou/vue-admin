<script setup lang="ts">
import { computed, onMounted, ref, watch } from "vue";

import IconBars3CenterLeft from "../components/icons/IconBars3CenterLeft.vue";
import IconXMark from "../components/icons/IconXMark.vue";
import IconMagnifyingGlass from "../components/icons/IconMagnifyingGlass.vue";
import IconUserCircle from "../components/icons/IconUserCircle.vue";
import IconLanguage from "../components/icons/IconLanguage.vue";

// Show or hide aside menu.
let isActivedAside = ref(false);
function setAsideStatus() {
  isActivedAside.value = !isActivedAside.value;
}

onMounted(() => {
  //
});
</script>

<template>
  <div class="bg-white border-b border-gray-200 fixed z-30 w-full">
    <div class="flex items-center justify-between">
      <div class="flex items-center justify-start">
        <button
          @click="setAsideStatus()"
          aria-expanded="true"
          aria-controls="sidebar"
          class="text-white bg-blue-500 cursor-pointer p-3 hover:bg-blue-600"
        >
          <IconBars3CenterLeft :class="{ hidden: isActivedAside }" />
          <IconXMark :class="{ hidden: !isActivedAside }" />
        </button>
        <a href="#" class="text-xl font-bold flex items-center lg:ml-2.5">
          <img src="@/assets/logo.svg" class="h-6 mr-2" alt="Windster Logo" />
          <span class="self-center whitespace-nowrap">Dashboard</span>
        </a>
        <form action="#" method="GET" class="hidden lg:block lg:pl-32">
          <label for="topbar-search" class="sr-only">Search</label>
          <div class="mt-1 relative lg:w-64">
            <div
              class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
            >
              <IconMagnifyingGlass />
            </div>
            <input
              type="text"
              name="email"
              id="topbar-search"
              class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm focus:ring-cyan-600 focus:border-cyan-600 block w-full pl-8 p-1"
              placeholder="Search"
            />
          </div>
        </form>
      </div>
      <div class="flex items-center">
        <button
          id="toggleSidebarMobileSearch"
          type="button"
          class="lg:hidden text-gray-500 hover:text-gray-900 hover:bg-gray-100 p-2 rounded-lg"
        >
          <span class="sr-only">Search</span>
          <IconMagnifyingGlass />
        </button>
        <div class="hidden lg:flex items-center">
          <div class="mr-3">
            <IconLanguage />
          </div>
          <div class="mr-3">
            <IconUserCircle class="text-gray-500" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
