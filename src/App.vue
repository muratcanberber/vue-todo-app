<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <nav class="navbar has-background-dark has-text-white">
    <div class="navbar-brand">
      <img src="../public/logo.png" class="image" />
    </div>
    <RouterLink to="/" class="navbar-item navbar-center px-8" id="menuItem"
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
