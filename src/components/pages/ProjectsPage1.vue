<template>
  <div class="h-full overflow-y-auto p-4 sm:p-6 space-y-5">
    <div class="border-b-2 border-blue-500 pb-3">
      <h2 class="text-2xl sm:text-3xl font-bold text-gray-800">Projects</h2>
      <p class="text-sm text-gray-500 mt-1">Part 1 of 3 · Featured work</p>
    </div>

    <!-- Synch Travel - Featured -->
    <div class="space-y-3 rounded-xl border-2 border-emerald-200 bg-emerald-50/50 p-4">
      <div class="flex flex-wrap items-center gap-2">
        <h3 class="text-lg sm:text-xl font-bold text-gray-800">Synch Travel Booking System</h3>
        <span class="px-2 py-0.5 bg-emerald-600 text-white rounded-full text-[10px] font-bold uppercase tracking-wide">Featured</span>
      </div>
      <p class="text-xs text-emerald-700 font-semibold">Multi-Tenant · B2B & B2C · Booking.com-style</p>
      <p class="text-sm text-gray-700 leading-relaxed">
        Scalable multi-tenant travel platform with custom client dashboards, Stripe payments,
        WhatsApp, and Twilio — plus deep 3rd-party travel API integrations for hotels, flights,
        activities, and transfers.
      </p>

      <div class="space-y-2 text-xs sm:text-sm text-gray-700">
        <p><span class="font-semibold text-slate-800">Hotelbeds:</span> Hotel API · Activity · Transfer</p>
        <p><span class="font-semibold text-slate-800">Flights:</span> Duffel · PKFare</p>
        <p><span class="font-semibold text-slate-800">Hotels:</span> Custom · SynchTravel · Hotelbeds · Hotelston · LiteAPI · Sunhotel · Stuba · Travelenda</p>
      </div>

      <a href="https://system.synchtravel.com/login" target="_blank" rel="noopener noreferrer"
         class="inline-flex items-center text-blue-600 hover:text-blue-700 text-sm font-medium break-all">
        <span>system.synchtravel.com</span>
        <svg class="w-4 h-4 ml-1 shrink-0" fill="currentColor" viewBox="0 0 20 20">
          <path d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z"/>
          <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z"/>
        </svg>
      </a>
      <div class="flex flex-wrap gap-2 pt-1">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">Multi-Tenant</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">Hotelbeds</span>
        <span class="px-2 py-1 bg-sky-100 text-sky-700 rounded text-xs font-medium">Duffel</span>
        <span class="px-2 py-1 bg-indigo-100 text-indigo-700 rounded text-xs font-medium">LiteAPI</span>
        <span class="px-2 py-1 bg-purple-100 text-purple-700 rounded text-xs font-medium">Stripe</span>
        <span class="px-2 py-1 bg-yellow-100 text-yellow-700 rounded text-xs font-medium">Twilio</span>
      </div>
    </div>

    <div class="border-t border-gray-200"></div>

    <!-- Live Comm System - New -->
    <div class="space-y-3 rounded-xl border-2 border-indigo-200 bg-indigo-50/40 p-4">
      <div class="flex flex-wrap items-center gap-2">
        <h3 class="text-lg sm:text-xl font-bold text-gray-800">Live Chat & Call Management System</h3>
        <span class="px-2 py-0.5 bg-indigo-600 text-white rounded-full text-[10px] font-bold uppercase tracking-wide">New</span>
      </div>
      <p class="text-xs text-indigo-700 font-semibold">Python · FastAPI · Vue.js · PostgreSQL</p>
      <p class="text-sm text-gray-700 leading-relaxed">
        Full management platform for realtime communication: live chat, video calls, and
        audio calls. Includes admin management, profile management, call logs, chat history,
        and complete operational control for teams.
      </p>
      <div class="flex flex-wrap gap-2 pt-1">
        <span class="px-2 py-1 bg-yellow-100 text-yellow-800 rounded text-xs font-medium">Python</span>
        <span class="px-2 py-1 bg-teal-100 text-teal-700 rounded text-xs font-medium">FastAPI</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">Vue.js</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">PostgreSQL</span>
        <span class="px-2 py-1 bg-rose-100 text-rose-700 rounded text-xs font-medium">Video / Audio Call</span>
        <span class="px-2 py-1 bg-violet-100 text-violet-700 rounded text-xs font-medium">Live Chat</span>
      </div>
    </div>

    <div class="border-t border-gray-200"></div>

    <!-- InkApp -->
    <div class="space-y-3">
      <h3 class="text-lg sm:text-xl font-bold text-gray-800">InkApp</h3>
      <p class="text-sm text-gray-700 leading-relaxed">
        Digital claim platform with automated PDF generation and claimant detail management.
        Integrated DocuSign for secure e-signatures and Twilio SMS for real-time notifications.
      </p>
      <a href="https://ink.testerp.co/" target="_blank" rel="noopener noreferrer"
         class="inline-flex items-center text-blue-600 hover:text-blue-700 text-sm font-medium">
        <span>ink.testerp.co</span>
        <svg class="w-4 h-4 ml-1" fill="currentColor" viewBox="0 0 20 20">
          <path d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z"/>
          <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z"/>
        </svg>
      </a>
      <div class="flex flex-wrap gap-2 pt-1">
        <span class="px-2 py-1 bg-red-100 text-red-700 rounded text-xs font-medium">Laravel</span>
        <span class="px-2 py-1 bg-blue-100 text-blue-700 rounded text-xs font-medium">PDF Generation</span>
        <span class="px-2 py-1 bg-green-100 text-green-700 rounded text-xs font-medium">DocuSign</span>
        <span class="px-2 py-1 bg-purple-100 text-purple-700 rounded text-xs font-medium">Twilio SMS</span>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>
