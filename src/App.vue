<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <div class="wrapper">
      <!-- <nav>
        <RouterLink to="/">Home</RouterLink> |
        <RouterLink to="/about">About</RouterLink> |
        <RouterLink to="/create">Add Product</RouterLink> |
        <RouterLink to="/list">List Product</RouterLink> |
        <RouterLink to="/payment">Pay out</RouterLink>
      </nav> -->
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

</style>
