<script setup lang="ts">
import { useStorage } from '@vueuse/core'
import { storageDemo } from '~/logic/storage'
const localstorageDemo = useStorage('localstorageDemo', 'localstorage')
watch(localstorageDemo, (val) => {
  console.log(val)
}, { immediate: true })
</script>

<template>
  <main class="px-4 py-10 text-center text-gray-700 dark:text-gray-200">
    <img src="/assets/icon.svg" class="icon-btn mx-2 text-2xl" alt="extension icon">
    <div>Options</div>
    <p class="mt-2 opacity-50">
      This is the options page
    </p>

    <div class="mt-3">
      storageDemo :
    </div>
    <input v-model="storageDemo" class="border border-gray-400 rounded px-2 py-1 mt-2">

    <div class="mt-3">
      localstorage with useStorage :
    </div>
    <input v-model="localstorageDemo" class="border border-gray-400 rounded px-2 py-1 mt-2">

    <div class="mt-4">
      Powered by Vite <pixelarticons-zap class="align-middle inline-block" />
    </div>
  </main>
</template>
