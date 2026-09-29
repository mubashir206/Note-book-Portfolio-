<template>
  <div class="h-full overflow-y-auto p-4 sm:p-6 space-y-5">
    <div class="border-b-2 border-blue-500 pb-3">
      <h2 class="text-2xl sm:text-3xl font-bold text-gray-800">Projects</h2>
      <p class="text-sm text-gray-500 mt-1">Part 3 of 3</p>
    </div>

    <!-- Asset Management -->
    <div class="space-y-3">
      <h3 class="text-lg sm:text-xl font-bold text-gray-800">Asset Management Platform</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        Platform to track company assets with employee assignments, activity history,
        and QR code–based instant access.
      </p>
      <div class="flex flex-wrap gap-2 pt-1">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">Asset Tracking</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">QR Code</span>
      </div>
    </div>

    <div class="border-t border-gray-200"></div>

    <div class="border-t border-gray-200"></div>

    <!-- Synch Travel API integrations -->
    <div class="space-y-3 rounded-xl bg-emerald-50/70 border border-emerald-200 p-4">
      <h3 class="text-lg sm:text-xl font-bold text-gray-800">Synch Travel — API Integrations</h3>
      <ul class="space-y-2 text-sm text-gray-700">
        <li class="flex items-start gap-2">
          <span class="text-emerald-600 font-bold shrink-0">•</span>
          <span><strong>Hotelbeds:</strong> Hotel API, Activity API, Transfer API</span>
        </li>
        <li class="flex items-start gap-2">
          <span class="text-emerald-600 font-bold shrink-0">•</span>
          <span><strong>Flights:</strong> Duffel, PKFare</span>
        </li>
        <li class="flex items-start gap-2">
          <span class="text-emerald-600 font-bold shrink-0">•</span>
          <span><strong>Hotels:</strong> Custom, SynchTravel, Hotelbeds, Hotelston, LiteAPI, Sunhotel, Stuba, Travelenda</span>
        </li>
        <li class="flex items-start gap-2">
          <span class="text-emerald-600 font-bold shrink-0">•</span>
          <span><strong>Also:</strong> Stripe payments, WhatsApp & Twilio notifications</span>
        </li>
      </ul>
    </div>

    <!-- Live Comm details expanded -->
    <div class="space-y-3 rounded-xl bg-slate-50 border border-slate-200 p-4">
      <h3 class="text-lg sm:text-xl font-bold text-gray-800">Live Chat & Call — Core Modules</h3>
      <p class="text-sm text-gray-600">
        Built with <strong>Python</strong>, <strong>FastAPI</strong>, <strong>Vue.js</strong>, and <strong>PostgreSQL</strong>.
      </p>
      <ul class="space-y-2 text-sm text-gray-700">
        <li class="flex items-start gap-2">
          <span class="text-indigo-600 font-bold shrink-0">•</span>
          <span><strong>Live Chat</strong> — realtime messaging with full chat history</span>
        </li>
        <li class="flex items-start gap-2">
          <span class="text-indigo-600 font-bold shrink-0">•</span>
          <span><strong>Video & Audio Calls</strong> — in-app calling with call logs</span>
        </li>
        <li class="flex items-start gap-2">
          <span class="text-indigo-600 font-bold shrink-0">•</span>
          <span><strong>Admin Management</strong> — roles, users, and system control</span>
        </li>
        <li class="flex items-start gap-2">
          <span class="text-indigo-600 font-bold shrink-0">•</span>
          <span><strong>Profile Management</strong> — user profiles and preferences</span>
        </li>
        <li class="flex items-start gap-2">
          <span class="text-indigo-600 font-bold shrink-0">•</span>
          <span><strong>Call Logs & Chat History</strong> — searchable operational records</span>
        </li>
      </ul>
    </div>

    <div class="p-4 bg-blue-50 rounded-lg border border-blue-200">
      <p class="text-sm text-gray-700 leading-relaxed">
        Focus across projects: scalable backends, clean Vue UIs, and reliable
        3rd-party integrations for real business workflows.
      </p>
    </div>
  </div>
</template>

<script setup>
</script>
