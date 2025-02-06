<template>
    <div class="flex items-center justify-center p-8">
        <div class="w-full max-w-4xl rounded-2xl shadow-xl p-12">
            <!-- Título -->
            <div class="flex items-center gap-4 mb-8">
                <slot name="title"></slot>
                <svg class="w-12 h-12 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 8h14M5 8a2 2 0 110-4h14a2 2 0 110 4M5 8v10a2 2 0 002 2h10a2 2 0 002-2V8m-9 4h4"/>
                </svg>
                <h1 class="text-4xl font-bold text-gray-800">
                    Gestión de Dependencias Simplificada
                </h1>
            </div>

            <!-- Contenido -->
            <div class="grid grid-cols-2 gap-8">
                <!-- Columna Izquierda -->
                <div class="space-y-6">
                    <div class="p-6 bg-emerald-50 rounded-xl">
                        <h3 class="flex items-center gap-2 text-lg font-semibold mb-3 text-emerald-800">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>
                            </svg>
                            Starters Oficiales
                        </h3>
                        <ul class="list-disc pl-5 space-y-2 text-gray-600">
                            <li>spring-boot-starter-web</li>
                            <li>spring-boot-starter-data-jpa</li>
                            <li>spring-boot-starter-security</li>
                        </ul>
                    </div>

                    <div class="p-6 bg-blue-50 rounded-xl">
                        <h3 class="flex items-center gap-2 text-lg font-semibold mb-3 text-blue-800">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"/>
                            </svg>
                            Auto-configuración
                        </h3>
                        <p class="text-gray-600">
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
                <div class="bg-gray-50 rounded-xl p-6">
                    <h3 class="flex items-center gap-2 text-lg font-semibold mb-4 text-gray-800">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l3 3-3 3m5 0h3M5 20h14a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/>
                        </svg>
                        Ejemplo pom.xml
                    </h3>
                    <slot name="code"></slot>
                </div>
            </div>

            <!-- Footer -->
            <div class="mt-8 pt-6 border-t border-gray-200 flex justify-between items-center text-sm text-gray-500">
                <div>spring.io/guides</div>
                <div>@SpringBoot</div>
            </div>
        </div>
    </div>
</template>
<style scoped>
</style>