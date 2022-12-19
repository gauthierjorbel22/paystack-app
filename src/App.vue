<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <div class="wrapper">
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <RouterLink class="btn" to="/">Home</RouterLink> |
        <RouterLink class="btn" to="/create">Add Product</RouterLink>|
        <RouterLink class="btn" to="/list">List Product</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
.btn:hover {
  color: white;
  background-color: rgb(7, 75, 139);
}
</style>
