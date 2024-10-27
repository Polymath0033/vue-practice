<template>
  <div class="w-80 space-y-3 rounded-lg bg-white px-5 py-3 text-sm shadow-sm">
    <div class="flex items-center gap-2">
      <img :src="avatar" :alt="name" class="size-8 rounded-full" />
      <div>
        <div class="font-medium">{{ name }}</div>
        <div class="text-xs text-stone-600">{{ title }}</div>
      </div>
    </div>
    <five-stars />
    <div class="whitespace-pre-line text-stone-600">{{ content }}</div>
  </div>
</template>

<script setup lang="ts">
import FiveStars from "./five-stars.vue";
defineProps<{
  name: string;
  title: string;
  avatar: string;
  content: string;
}>();
</script>

<style scoped></style>
