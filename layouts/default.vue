<template>

  <div class="drawer">
    <input
      id="my-side-drawer"
      ref="drawerInput"
      type="checkbox"
      class="drawer-toggle"
      v-model="drawerOpen"
    />
    <div class="drawer-content flex flex-col">
      <!-- Navbar -->
      <div class="w-full navbar max-w-screen-2xl m-auto">
        <div class="flex-none lg:hidden">
          <label
            for="my-side-drawer"
            aria-label="open sidebar"
            class="btn btn-square btn-ghost"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              class="inline-block w-6 h-6 stroke-current"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              ></path>
            </svg>
          </label>
        </div>
        <div class="flex-1 justify-between">
          <div class="">
            <NuxtLink
              to="/"
              class="logo-dark hidden"
            >
              Home
            </NuxtLink>
            <NuxtLink
              to="/"
              class="logo-light hidden"
            >
              Home
              >
            </NuxtLink>
          </div>
          <details
            class="dropdown dropdown-end"
            ref="toolsDropdown"
            @mouseenter="openToolsMenu"
            @mouseleave="closeToolsMenu"
            @focus="openToolsMenu"
            @blur="closeToolsMenu"
          >
            <summary class="btn btn-ghost m-1">
              Tools

            </summary>
            <ul class="menu dropdown-content bg-base-200 rounded-box z-[1] w-52 p-2 shadow">
              <li>
                <NuxtLink
                  class=""
                  to="/ai-face-shape-analysis"
                >
                  Option 1
                </NuxtLink>
              </li>
              <li>
                <NuxtLink
                  class=""
                  to="/hair"
                >
                  Option 2
                </NuxtLink>
              </li>
              <li>
                <NuxtLink
                  to="/hair-colour-changer"
                  class=""
                >
                  Option 3
                </NuxtLink>
              </li>
            </ul>
          </details>
        </div>
        <div class="flex-none">
          Top navbar
        </div>
      </div>
      <!-- Page content here -->
      <slot />
    </div>
    <div class="drawer-side z-30">
      <label
        ref="drawerLabel"
        for="my-side-drawer"
        aria-label="close sidebar"
        class="drawer-overlay"
      ></label>
      <div class="menu p-4 w-80 min-h-full bg-base-200 text-base-content z-50">
        <p>
          <NuxtLink to="/">Home</NuxtLink>
        </p>
      </div>

    </div>
  </div>

</template>

<style>
  
.pageContent {
  min-height: 70vh;
  height: 100%;
}

</style>

<script setup>

import { useRoute } from 'vue-router'

const drawerLabel = ref(null)
const route = useRoute()
const drawerInput = ref(null)
const drawerOpen = ref(false)
const toolsDropdown = ref(null)

watch(() => route.path, (newPath, oldPath) => {
  console.log('route changed:', newPath)
  if (drawerLabel.value) {
    drawerOpen.value = false
  }

  if (toolsDropdown.value && toolsDropdown.value.open) {
    toolsDropdown.value.removeAttribute('open');
  } 
  
})

function closeDrawer() {
  drawerOpen.value = false
}

// hotfix to add the google script to the head
useHead({
  script: [
    {
      src: 'https://accounts.google.com/gsi/client',
      defer: true,
      async: true
    }
  ]
})

function openToolsMenu() {
  toolsDropdown.value.setAttribute('open', '');
}

function closeToolsMenu() {
  toolsDropdown.value.removeAttribute('open');
}

</script>