<template>
  <div class="h-full flex items-center justify-center p-6 bg-gradient-to-br from-slate-50 via-blue-50 to-purple-50">
    <div class="max-w-4xl w-full space-y-8">
      <!-- Header -->
      <div class="text-center space-y-3">
        <h2 class="text-4xl md:text-5xl font-bold text-slate-800">
          About Me
        </h2>
        <div class="h-1 w-20 mx-auto bg-gradient-to-r from-blue-600 to-purple-600 rounded-full"></div>
      </div>

      <!-- Introduction Card -->
      <div class="bg-white/90 backdrop-blur-sm rounded-2xl p-6 shadow-md border border-slate-200">
        <p class="text-base md:text-lg text-slate-700 leading-relaxed text-center">
          Experienced <span class="font-semibold text-slate-800">Laravel developer</span> with a strong background in web application development and a proven 
          track record of delivering <span class="font-semibold text-slate-800">high-quality, scalable solutions</span>.
        </p>
      </div>

      <!-- Contact Information Grid -->
      <div class="grid grid-cols-2 gap-4">
        <!-- Email -->
        <div class="group bg-slate-700 hover:bg-slate-600 rounded-xl p-4 text-white shadow-md hover:shadow-lg transition-all duration-300 cursor-pointer border border-slate-600">
          <div class="flex flex-col items-center text-center space-y-2">
            <div class="p-2 bg-slate-600 rounded-lg group-hover:bg-slate-500 transition-colors">
              <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
                <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"/>
                <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"/>
              </svg>
            </div>
            <div>
              <p class="text-xs text-slate-300">Email</p>
              <p class="font-semibold text-sm break-all">mh2603391@gmail.com</p>
            </div>
          </div>
        </div>

        <!-- Phone -->
        <div class="group bg-slate-700 hover:bg-slate-600 rounded-xl p-4 text-white shadow-md hover:shadow-lg transition-all duration-300 cursor-pointer border border-slate-600">
          <div class="flex flex-col items-center text-center space-y-2">
            <div class="p-2 bg-slate-600 rounded-lg group-hover:bg-slate-500 transition-colors">
              <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
                <path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z"/>
              </svg>
            </div>
            <div>
              <p class="text-xs text-slate-300">Phone</p>
              <p class="font-semibold text-sm">+923480464778</p>
            </div>
          </div>
        </div>

        <!-- Location -->
        <div class="group bg-slate-700 hover:bg-slate-600 rounded-xl p-4 text-white shadow-md hover:shadow-lg transition-all duration-300 cursor-pointer border border-slate-600">
          <div class="flex flex-col items-center text-center space-y-2">
            <div class="p-2 bg-slate-600 rounded-lg group-hover:bg-slate-500 transition-colors">
              <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd"/>
              </svg>
            </div>
            <div>
              <p class="text-xs text-slate-300">Location</p>
              <p class="font-semibold text-sm">Firdous Market, Lahore</p>
            </div>
          </div>
        </div>

        <!-- LinkedIn -->
        <div class="group bg-slate-700 hover:bg-slate-600 rounded-xl p-4 text-white shadow-md hover:shadow-lg transition-all duration-300 cursor-pointer border border-slate-600">
          <div class="flex flex-col items-center text-center space-y-2">
            <div class="p-2 bg-slate-600 rounded-lg group-hover:bg-slate-500 transition-colors">
              <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
              </svg>
            </div>
            <div>
              <p class="text-xs text-slate-300">LinkedIn</p>
              <p class="font-semibold text-sm">Mubashir-Hussain</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>

