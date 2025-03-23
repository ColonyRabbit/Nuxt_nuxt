<template lang="">
  <div class="py-4 w-screen">
    <OrgChart />
  </div>
</template>

<script setup>
import OrgChart from "@/components/Homepage/OrgChart.vue";
import { useHead } from "@vueuse/head";

useHead({
  title: "Home",
});
</script>
<style lang=""></style>
