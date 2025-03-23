<template>
  <div class="p-4"><TimelineMe /></div>
</template>

<script setup>
import TimelineMe from "@/components/About/TimelineMe.vue";
import { useHead } from "@vueuse/head";

useHead({
  title: "About",
});
</script>
<style lang=""></style>
