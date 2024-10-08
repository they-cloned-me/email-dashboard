<template>
  <header class="bg-[#FAFAF8] p-4 flex justify-between items-center border-b border-[#E5E5E3] z-10">
    <div class="flex items-center space-x-2">
      <div class="w-8 h-8 bg-perlon-orange rounded-md flex items-center justify-center text-black font-bold text-xl">r</div>
      <span class="text-xl font-semibold">random</span>
    </div>
    <div class="flex space-x-4">
      <button v-for="(icon, index) in headerIcons" :key="index" class="text-gray-600 hover:text-gray-800">
        <div class="bg-white p-1.5 rounded shadow-sm">
          <component :is="icon" class="w-5 h-5" />
        </div>
      </button>
    </div>
  </header>
</template>

<script setup>
import { QuestionMarkCircleIcon, ChatBubbleLeftIcon, BellIcon } from '@heroicons/vue/24/outline'

const headerIcons = [QuestionMarkCircleIcon, ChatBubbleLeftIcon, BellIcon]
</script>