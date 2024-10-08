<template>
  <div>
    <h1 class="text-3xl font-semibold mb-8 text-gray-800">Pending Approval</h1>
    <div class="bg-white rounded-lg shadow-sm border border-gray-200 overflow-hidden">
      <ul class="divide-y divide-gray-200">
        <li v-for="item in pendingApprovals" :key="item.id" class="p-6 sm:py-4 sm:px-6">
          <div class="flex items-center justify-between">
            <div>
              <h3 class="text-lg font-medium text-gray-900">{{ item.title }}</h3>
              <div class="mt-1 flex items-center text-sm text-gray-500">
                <UserIcon class="flex-shrink-0 mr-1.5 h-4 w-4 text-gray-400" />
                <span>{{ item.requester }}</span>
                <span class="mx-2">&middot;</span>
                <CalendarIcon class="flex-shrink-0 mr-1.5 h-4 w-4 text-gray-400" />
                <span>{{ item.date }}</span>
              </div>
              <p class="mt-2 text-sm text-gray-600">{{ item.description }}</p>
            </div>
            <div class="flex space-x-2 absolute right-12 top-0">
              <button @click="approveItem(item.id)" class="p-2 rounded-full bg-green-100 text-green-600 hover:bg-green-200 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500">
                <span class="sr-only">Approve</span>
                <CheckIcon class="h-5 w-5" />
              </button>
              <button @click="declineItem(item.id)" class="p-2 rounded-full bg-red-100 text-red-600 hover:bg-red-200 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500">
                <span class="sr-only">Decline</span>
                <XMarkIcon class="h-5 w-5" />
              </button>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { UserIcon, CalendarIcon, CheckIcon, XMarkIcon } from '@heroicons/vue/24/outline'

const pendingApprovals = ref([
  {
    id: 1,
    title: 'New Email Campaign: Summer Sale',
    requester: 'John Doe',
    date: 'May 15, 2023',
    description: 'Approval needed for the new summer sale email campaign targeting our premium customers.'
  },
  {
    id: 2,
    title: 'User List Segmentation',
    requester: 'Jane Smith',
    date: 'May 14, 2023',
    description: 'Request to approve the new user list segmentation for targeted marketing efforts.'
  },
  {
    id: 3,
    title: 'Integration with CRM System',
    requester: 'Mike Johnson',
    date: 'May 13, 2023',
    description: 'Approval required for integrating our email marketing platform with the new CRM system.'
  }
])

const approveItem = (id) => {
  console.log(`Approved item ${id}`)
  pendingApprovals.value = pendingApprovals.value.filter(item => item.id !== id)
}

const declineItem = (id) => {
  console.log(`Declined item ${id}`)
  pendingApprovals.value = pendingApprovals.value.filter(item => item.id !== id)
}
</script>