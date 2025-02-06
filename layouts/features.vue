<script lang="ts" setup>

const props = defineProps<{
  image: string;
  altImage: string;
}>();

</script>

<template>
  <section class="section">
    <div class="left">
      <slot />
      <div class="mt-6 aspect-ratio-video rounded-sm">
        <img v-if="image" :src="props.image" :alt="altImage" class="object-top-left" />
      </div>
    </div>
    <hr class="w-1 top-50% h-32 bg-gray-100 border-0 rounded-sm dark:bg-gray-700">
    <div class="right">
      <slot name="features" />
    </div>
  </section>
</template>
<style scoped>
.section {
  --uno: 'flex flex-row h-full justify-stretch  items-center select-auto space-x-4 px-4 py-4';
}

/* LEFT */
.section .left {
  --uno: 'flex-1 w-full';
}

.section .left :deep(h1) {
  --uno: 'text-3xl mb-4 font-bold text-center';
}

.section .left :deep(p) {
  --uno: 'text-md font-extralight';
}

/* RIGHT */
.section .right {
  --uno: 'flex-1 w-full overflow-hidden';
}

.section .right :deep(ul) {
  --uno: 'space-y-2 block h-fit-content';
}

.section .right :deep(ul li) {
  --uno: '';
}

.section .right :deep(ul li h3) {
  --uno: 'font-size-lg font-bold color-emerald-500';
}

.section .right :deep(ul li h3 svg) {
  --uno: 'w-1em h-1em fill-current mr-2 inline-block align-middle';
}

.section .right :deep(ul li p) {
  --uno: 'font-size-sm font-thin ml-7';
}
</style>
