<template>
  <div>
    <h1 class="text-3xl font-semibold mb-8">Mailboxes</h1>
    <div class="bg-white rounded-lg p-8 text-center">
      <img src="/mailbox-icon.svg" alt="Mailbox icon" class="w-20 h-20 mx-auto mb-4">
      <h2 class="text-xl font-semibold mb-2">You have no mailboxes connected at this time.</h2>
      <p class="text-gray-600 mb-6">Connect a mailbox using the buttons below.</p>
      <div class="flex justify-center flex-col-reverse md:flex-row gap-2 md:gap-4">
        <button class="bg-white text-gray-700 border border-gray-300 px-4 py-2 rounded-md hover:bg-gray-50 flex items-center">
          <InboxIcon class="w-5 h-5 mr-2" />
          Connect IMAP
        </button>
        <button class="border border-gray-500 bg-perlon-orange text-black px-4 py-2 rounded-md hover:bg-orange-600 flex items-center">
          <ArrowRightOnRectangleIcon class="w-5 h-5 mr-2" />
          Connect Gmail/Outlook
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { InboxIcon, ArrowRightOnRectangleIcon } from '@heroicons/vue/24/outline'
</script>