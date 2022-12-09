<script setup lang="ts">
import { useStorage } from '@vueuse/core'
import { storageDemo } from '~/logic/storage'
const localstorageDemo = useStorage('localstorageDemo', 'localstorage')
watch(localstorageDemo, (val) => {
  console.log(val)
}, { immediate: true })

function openOptionsPage() {
  browser.runtime.openOptionsPage()
}
</script>

<template>
  <main class="w-[300px] px-4 py-5 text-center text-gray-700">
    <Logo />
    <div>Popup</div>
    <p class="mt-2 opacity-50">
      This is the popup page
    </p>

    <div class="mt-3">
      storageDemo :
    </div>
    <input v-model="storageDemo" class="border border-gray-400 rounded px-2 py-1 mt-2">

    <div class="mt-3">
      localstorage with useStorage :
    </div>
    <input v-model="localstorageDemo" class="border border-gray-400 rounded px-2 py-1 mt-2">

    <button class="btn mt-2" @click="openOptionsPage">
      Open Options
    </button>
    <div class="mt-2">
      <span class="opacity-50">Storage:</span> {{ storageDemo }}
    </div>
  </main>
</template>
