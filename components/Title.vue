<script setup lang="ts">

const props = defineProps<{
  icon: string;
}>();

</script>

<template>
  <div class="inline-flex items-center align-item-start w-full font-size-md font-bold">
    <span :class="props.icon" class="w-1.5em h-1.5em" />
    <h3><slot /></h3>
  </div>
</template>

<style scoped>
:deep(h3) {
  --uno: 'ml-2 hover:underline';
}


</style>