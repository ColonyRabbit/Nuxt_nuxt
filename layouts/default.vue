<template lang="html">
  <div class="card">
    <Header />
    <slot />
  </div>
</template>

<script setup>
import Header from "@/components/Header.vue";
</script>
