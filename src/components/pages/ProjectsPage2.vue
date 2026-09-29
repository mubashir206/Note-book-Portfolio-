<template>
  <div class="h-full overflow-y-auto p-4 sm:p-6 space-y-5">
    <div class="border-b-2 border-blue-500 pb-3">
      <h2 class="text-2xl sm:text-3xl font-bold text-gray-800">Projects</h2>
      <p class="text-sm text-gray-500 mt-1">Part 2 of 3</p>
    </div>

    <!-- Taif Shipping ERP -->
    <div class="space-y-3">
      <h3 class="text-lg sm:text-xl font-bold text-gray-800">Taif Shipping ERP System</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        ERP for sand shipping — inventory, orders, multi-stage shipping, reporting, and HRM
        functions like attendance, leave, and holidays to improve operations.
      </p>
      <a href="https://taif-shipping.testerp.co/dashboard" target="_blank" rel="noopener noreferrer"
         class="inline-flex items-center text-blue-600 hover:text-blue-700 text-sm font-medium break-all">
        <span>taif-shipping.testerp.co</span>
        <svg class="w-4 h-4 ml-1 shrink-0" fill="currentColor" viewBox="0 0 20 20">
          <path d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z"/>
          <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z"/>
        </svg>
      </a>
      <div class="flex flex-wrap gap-2 pt-1">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">ERP</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">Inventory</span>
        <span class="px-2 py-1 bg-yellow-100 text-yellow-700 rounded text-xs font-medium">HRM</span>
      </div>
    </div>

    <div class="border-t border-gray-200"></div>

    <!-- HRM System -->
    <div class="space-y-3">
      <h3 class="text-lg sm:text-xl font-bold text-gray-800">HRM System</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        Complete HRM platform with attendance & leave tracking, payroll & finance, task
        scheduling, team communication, performance evaluation, holidays, and analytics.
      </p>
      <a href="https://attendance.maqware.com" target="_blank" rel="noopener noreferrer"
         class="inline-flex items-center text-blue-600 hover:text-blue-700 text-sm font-medium">
        <span>attendance.maqware.com</span>
        <svg class="w-4 h-4 ml-1" fill="currentColor" viewBox="0 0 20 20">
          <path d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z"/>
          <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z"/>
        </svg>
      </a>
      <div class="flex flex-wrap gap-2 pt-1">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">HRM</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">Payroll</span>
        <span class="px-2 py-1 bg-purple-100 text-purple-700 rounded text-xs font-medium">Analytics</span>
      </div>
    </div>

    <div class="border-t border-gray-200"></div>

    <!-- Insurance Claim -->
    <div class="space-y-3">
      <h3 class="text-lg sm:text-xl font-bold text-gray-800">Insurance Claim System</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        Digital claim workflow with automated PDF generation, claimant management,
        DocuSign e-signatures, and Twilio SMS for faster paperless processing.
      </p>
      <div class="flex flex-wrap gap-2 pt-1">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">Insurance</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">DocuSign</span>
        <span class="px-2 py-1 bg-yellow-100 text-yellow-700 rounded text-xs font-medium">Twilio SMS</span>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>
