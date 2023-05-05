<template>
  <div class="about">
    <h1>About page</h1>
    <p>
      Prank! Just adding a second page to navigate to using the RouterLink.
    </p>
    <p>
      <RouterLink class="underline" to="/">Back to home</RouterLink>
    </p>
  </div>
</template>
<script setup>
import { RouterLink } from 'vue-router'
</script>
