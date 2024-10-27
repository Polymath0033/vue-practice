<script setup lang="ts">
const {
  direction = "left",
  pauseOnHover = false,
  reverse = false,
  fade = true,
  numberOfCopies = 2,
} = defineProps<{
  direction?: "left" | "right";
  pauseOnHover?: boolean;
  reverse?: boolean;
  fade?: boolean;
  className?: string;
  innerClassName?: string;
  numberOfCopies?: number;
}>();
</script>
<template>

  <div
    :class="['group flex gap-[1rem] overflow-hidden', className]"
    :style="{
      'mask-image': fade
        ? `linear-gradient(${
            direction === 'left' ? 'to right' : 'to bottom'
          }  transparent 0%, rgba(0, 0, 0, 1.0) 10%, rgba(0, 0, 0, 1.0) 90%, transparent 100%)`
    : 'none',
    WebkitMaskImage: fade
    ? `linear-gradient(to ${direction === 'left' ? 'right' : 'bottom'}, 
        transparent 0%, rgba(0, 0, 0, 1.0) 10%, 
        rgba(0, 0, 0, 1.0) 90%, transparent 100%)`
    : 'none'
      
    }"
    v-bind="$attrs" 
  >
    <div
      v-for="(_, i) in Array(numberOfCopies)"
      :key="i"
      :class="[
        'flex justify-around gap-[1rem] [--gap:1rem] shrink-0',
        direction == 'left'
          ? 'animate-marquee-left flex-row'
          : 'animate-marquee-up flex-col',
        pauseOnHover && 'group-hover:[animation-play-state:paused]',
        reverse && 'direction-reverse',
        innerClassName,
      ]"
    >
      <slot />
    </div>
  </div>
</template>

<style scoped></style>
