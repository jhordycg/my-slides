<script lang="ts" setup>

const props = defineProps<{
  filename: string;
}>();

</script>

<template>
  <div class="flex items-center justify-center h-full">
    <div class="w-full max-w-4xl rounded-2xl shadow-xl">
      <!-- Título -->
      <div class="flex items-center gap-4 mb-8">
        <slot name="title"></slot>
      </div>
      <!-- Contenido -->
      <div class="grid grid-cols-2 gap-8">
        <!-- Columna Izquierda -->
        <div class="space-y-6">
          <div class="p-6 bg-emerald-50 rounded-xl">
            <slot name="card-1"></slot>
          </div>
          <div class="p-6 bg-blue-50 rounded-xl">
            <h3 class="flex items-center gap-2 text-lg font-semibold mb-3 text-blue-800">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
              </svg>
              Auto-configuración
            </h3>
            <p class="text-gray-600 font-size-sm">
              Detecta dependencias y configura automáticamente:
            </p>
            <div class="mt-2 text-sm text-gray-500">
              <span class="px-2 py-1 bg-blue-100 rounded">Tomcat</span>
              <span class="px-2 py-1 bg-blue-100 rounded">Hibernate</span>
              <span class="px-2 py-1 bg-blue-100 rounded">Spring Security</span>
            </div>
          </div>
        </div>

        <!-- Columna Derecha -->
        <div class="bg-blue-100 rounded-xl p-6">
          <slot name="code"></slot>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
:deep(h1) {
  --uno: 'text-4xl font-bold';
}

:deep(h3) {
  --uno: 'flex items-center gap-2 text-lg font-semibold mb-3 text-emerald-800';
}

:deep(ul) {
  --uno: 'list-disc pl-5 space-y-2 text-gray-600 font-size-sm'
}

:deep(div > svg) {
  --uno: 'w-2.5em h-2.5em';
}
</style>