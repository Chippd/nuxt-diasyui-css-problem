<template>
  <div>
    <div class="text-sm breadcrumbs">
      <ul>
        <li><NuxtLink to="/">Home</NuxtLink></li>
        <li>{{ $route.params.slug.join(' / ') }}</li>
      </ul>
    </div>
    
    <h1>{{ $route.params.slug }}</h1>
  </div>

  <main>
    <ContentDoc />
  </main>
</template>

<style scoped>
.breadcrumbs {
  padding: 1rem 0;
}
</style>

<script setup>
const route = useRoute()
</script>