<template>
  <div class="about">
    <h1>{{str}}</h1>
  </div>
</template>

<script setup lang="ts">
  const str: String = 'This is an about page'
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
