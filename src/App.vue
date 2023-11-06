<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <nav class="navbar has-background-dark has-text-white">
    <div class="navbar-brand has-background-success px-6">
      <a class="navbar-item has-text-white is-size-4" href="/"> TODO </a>
    </div>
    <RouterLink to="/" class="navbar-item navbar-end" id="menuItem"
      >Home</RouterLink
    >
    <RouterLink to="/about" class="navbar-item" id="menuItem">About</RouterLink>
  </nav>
  <RouterView />
</template>

<style scoped>
@keyframes example {
  from {
    background-color: black;
  }
  to {
    background-color: white;
  }
}

#menuItem {
  color: white;
}
#menuItem:hover {
  color: black;
  animation-name: example;
  animation-duration: 0.5s;
}
</style>
