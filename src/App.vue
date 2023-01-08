<script setup>
import { RouterLink, RouterView } from 'vue-router'
import MenuSection from './components/MenuSection.vue'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </div>
  </header>
  <MenuSection />
  <RouterView />
</template>

<style scoped>

</style>
