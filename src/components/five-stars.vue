<template>
  <div class="flex items-center text-amber-400">
    <star-icon class="size-4" v-for="i in 5" :key="i" />
  </div>
</template>

<script setup lang="ts">
import StarIcon from "./star-icon.vue";
</script>

<style scoped></style>
