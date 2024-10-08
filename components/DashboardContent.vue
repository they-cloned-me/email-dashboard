<template>
  <div>
    <h1 class="text-3xl font-semibold mb-8 text-gray-800">Dashboard</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <div class="bg-white rounded-lg shadow-sm p-6 border border-gray-200">
        <h2 class="text-xl font-semibold mb-4 text-gray-800">Active Campaigns</h2>
        <div class="flex items-center justify-between">
          <div class="text-4xl font-bold text-perlon-orange">12</div>
          <div class="bg-orange-100 p-2 rounded-full">
            <ChartBarIcon class="w-6 h-6 text-perlon-orange" />
          </div>
        </div>
        <p class="text-sm text-gray-600 mt-2">3 campaigns ending this week</p>
      </div>
      <div class="bg-white rounded-lg shadow-sm p-6 border border-gray-200">
        <h2 class="text-xl font-semibold mb-4 text-gray-800">Total Subscribers</h2>
        <div class="flex items-center justify-between">
          <div class="text-4xl font-bold text-green-600">5,234</div>
          <div class="bg-green-100 p-2 rounded-full">
            <UsersIcon class="w-6 h-6 text-green-600" />
          </div>
        </div>
        <p class="text-sm text-gray-600 mt-2">+123 new subscribers this month</p>
      </div>
      <div class="bg-white rounded-lg shadow-sm p-6 border border-gray-200">
        <h2 class="text-xl font-semibold mb-4 text-gray-800">Engagement Rate</h2>
        <div class="flex items-center justify-between">
          <div class="text-4xl font-bold text-blue-600">68%</div>
          <div class="bg-blue-100 p-2 rounded-full">
            <ChartPieIcon class="w-6 h-6 text-blue-600" />
          </div>
        </div>
        <p class="text-sm text-gray-600 mt-2">5% increase from last month</p>
      </div>
    </div>
    <div class="mt-8 bg-white rounded-lg shadow-sm p-6 border border-gray-200">
      <h2 class="text-xl font-semibold mb-4 text-gray-800">Recent Activity</h2>
      <ul class="space-y-4">
        <li v-for="(activity, index) in recentActivities" :key="index" class="flex items-start">
          <div class="bg-gray-100 rounded-full p-1.5 mr-4">
            <component :is="activity.icon" class="w-4 h-4 text-gray-600" />
          </div>
          <div>
            <p class="font-semibold text-gray-800">{{ activity.title }}</p>
            <p class="text-sm text-gray-600">{{ activity.time }}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ChartBarIcon, UsersIcon, ChartPieIcon, EnvelopeIcon, BellIcon, UserPlusIcon } from '@heroicons/vue/24/outline'

const recentActivities = [
  { icon: EnvelopeIcon, title: 'New campaign "Summer Sale" created', time: '2 hours ago' },
  { icon: BellIcon, title: 'Reminder: Review pending approvals', time: '5 hours ago' },
  { icon: UserPlusIcon, title: '50 new subscribers added', time: 'Yesterday at 3:45 PM' },
]
</script>