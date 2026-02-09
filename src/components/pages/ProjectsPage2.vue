<template>
  <div class="space-y-6">
    <div class="border-b-2 border-blue-500 pb-3">
      <h2 class="text-3xl font-bold text-gray-800">Projects</h2>
      <p class="text-sm text-gray-500 mt-1">Part 2 of 2</p>
    </div>

    <!-- HRM System -->
    <div class="space-y-3">
      <h3 class="text-xl font-bold text-gray-800">HRM System</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        Developed a complete HRM platform with attendance & leave tracking, payroll & finance, task 
        scheduling, team communication, performance evaluation, holiday management, and analytics 
        streamlining HR operations and boosting productivity.
      </p>
      <a href="https://attendance.maqware.com" target="_blank" 
         class="inline-flex items-center text-blue-600 hover:text-blue-700 text-sm font-medium">
        <span>attendance.maqware.com</span>
        <svg class="w-4 h-4 ml-1" fill="currentColor" viewBox="0 0 20 20">
          <path d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z"/>
          <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z"/>
        </svg>
      </a>
      <div class="flex flex-wrap gap-2 pt-2">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">HRM</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">Payroll</span>
        <span class="px-2 py-1 bg-purple-100 text-purple-700 rounded text-xs font-medium">Analytics</span>
      </div>
    </div>

    <div class="border-t border-gray-200 my-4"></div>

    <!-- Insurance Claim System -->
    <div class="space-y-3">
      <h3 class="text-xl font-bold text-gray-800">Insurance Claim System</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        Developed a digital claim platform with automated PDF generation and claimant detail management. 
        Integrated DocuSign for secure e-signatures and Twilio SMS for real-time notifications, enabling 
        faster and paperless claim processing.
      </p>
      <div class="flex flex-wrap gap-2 pt-2">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">Insurance</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">DocuSign</span>
        <span class="px-2 py-1 bg-yellow-100 text-yellow-700 rounded text-xs font-medium">Twilio SMS</span>
      </div>
    </div>

    <div class="border-t border-gray-200 my-4"></div>

    <!-- Asset Management -->
    <div class="space-y-3">
      <h3 class="text-xl font-bold text-gray-800">Asset Management Platform</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        Built a platform to track company assets with employee assignments, activity history, and QR 
        code–based instant access.
      </p>
      <div class="flex flex-wrap gap-2 pt-2">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">Asset Tracking</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">QR Code</span>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>

