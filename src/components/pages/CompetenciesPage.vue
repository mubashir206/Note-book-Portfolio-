<template>
  <div class="h-full p-8 md:p-12 bg-gradient-to-br from-purple-50 to-pink-50 flex items-center justify-center">
    <div class="w-full">
    <div class="max-w-5xl mx-auto space-y-6">
      <!-- Header -->
      <div class="text-center space-y-3">
        <h2 class="text-4xl md:text-5xl font-bold text-slate-800">
          Skills & Expertise
        </h2>
        <div class="h-1 w-20 mx-auto bg-gradient-to-r from-purple-600 to-pink-600 rounded-full"></div>
      </div>

      <!-- Skills Grid -->
      <div class="grid grid-cols-2 md:grid-cols-3 gap-3">
        <!-- Backend Skills -->
        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">💻</div>
          <h3 class="text-xl font-bold mb-3">PHP & Laravel</h3>
          <p class="text-sm opacity-90">Expert in Laravel framework</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">⚛️</div>
          <h3 class="text-xl font-bold mb-3">React JS</h3>
          <p class="text-sm opacity-90">Modern React applications</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🎨</div>
          <h3 class="text-xl font-bold mb-3">Vue.js</h3>
          <p class="text-sm opacity-90">Progressive framework</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🔥</div>
          <h3 class="text-xl font-bold mb-3">JavaScript</h3>
          <p class="text-sm opacity-90">JS, jQuery, Ajax & ES6+</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🎯</div>
          <h3 class="text-xl font-bold mb-3">Tailwind CSS</h3>
          <p class="text-sm opacity-90">Utility-first CSS</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🛠️</div>
          <h3 class="text-xl font-bold mb-3">Bootstrap</h3>
          <p class="text-sm opacity-90">Responsive framework</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🗄️</div>
          <h3 class="text-xl font-bold mb-3">MySQL</h3>
          <p class="text-sm opacity-90">Database management</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🍃</div>
          <h3 class="text-xl font-bold mb-3">MongoDB</h3>
          <p class="text-sm opacity-90">NoSQL solutions</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🐍</div>
          <h3 class="text-xl font-bold mb-3">Python</h3>
          <p class="text-sm opacity-90">Scripting & automation</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">📦</div>
          <h3 class="text-xl font-bold mb-3">Node.js</h3>
          <p class="text-sm opacity-90">Server-side JavaScript</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🚀</div>
          <h3 class="text-xl font-bold mb-3">RESTful APIs</h3>
          <p class="text-sm opacity-90">API design & integration</p>
        </div>

        <div class="skill-card group bg-slate-700 hover:bg-slate-600 border border-slate-600">
          <div class="skill-icon">🔧</div>
          <h3 class="text-xl font-bold mb-3">Git & Tools</h3>
          <p class="text-sm opacity-90">Version control</p>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.skill-card {
  padding: 1rem;
  border-radius: 0.75rem;
  color: white;
  box-shadow: 0 10px 20px -5px rgba(0, 0, 0, 0.15);
  transition: all 0.3s;
  cursor: pointer;
  text-align: center;
}

.skill-card:hover {
  box-shadow: 0 20px 35px -8px rgba(0, 0, 0, 0.25);
  transform: translateY(-4px);
}

.skill-icon {
  font-size: 1.75rem;
  margin-bottom: 0.5rem;
  transition: transform 0.3s;
}

.group:hover .skill-icon {
  transform: scale(1.15);
}

.skill-card h3 {
  font-size: 1rem;
  margin-bottom: 0.25rem;
}

.skill-card p {
  font-size: 0.75rem;
  opacity: 0.9;
}
</style>

