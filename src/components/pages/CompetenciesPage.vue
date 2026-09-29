<template>
  <div class="page-shell">
    <div class="page-inner">
      <header class="text-center mb-4 sm:mb-5">
        <p class="eyebrow">Tech stack</p>
        <h2 class="title">Skills & Expertise</h2>
        <div class="accent-line"></div>
      </header>

      <section v-for="group in skillGroups" :key="group.title" class="skill-group">
        <div class="group-head">
          <span class="group-dot" :style="{ background: group.color }"></span>
          <h3>{{ group.title }}</h3>
        </div>
        <div class="chips">
          <span
            v-for="skill in group.skills"
            :key="skill"
            class="chip"
            :style="{ '--accent': group.color }"
          >
            {{ skill }}
          </span>
        </div>
      </section>
    </div>
  </div>
</template>

<script setup>
const skillGroups = [
  {
    title: 'Backend',
    color: '#ef4444',
    skills: ['PHP', 'Laravel', 'Python', 'FastAPI', 'Node.js', 'RESTful APIs'],
  },
  {
    title: 'Frontend',
    color: '#0ea5e9',
    skills: ['Vue.js', 'Vue 3', 'React', 'JavaScript', 'Tailwind CSS', 'Bootstrap'],
  },
  {
    title: 'Databases',
    color: '#10b981',
    skills: ['MySQL', 'PostgreSQL', 'MongoDB'],
  },
  {
    title: 'Hotelbeds APIs',
    color: '#0284c7',
    skills: ['Hotelbeds Hotel', 'Hotelbeds Activity', 'Hotelbeds Transfer'],
  },
  {
    title: 'Flight APIs',
    color: '#6366f1',
    skills: ['Duffel', 'PKFare'],
  },
  {
    title: 'Hotel APIs',
    color: '#14b8a6',
    skills: ['Custom', 'SynchTravel', 'Hotelbeds', 'Hotelston', 'LiteAPI', 'Sunhotel', 'Stuba', 'Travelenda'],
  },
  {
    title: 'Integrations & Tools',
    color: '#f59e0b',
    skills: ['Stripe', 'Twilio', 'WhatsApp', 'DocuSign', 'Git', 'Postman', 'Swagger', 'CPanel'],
  },
]
</script>

<style scoped>
.page-shell {
  height: 100%;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
  background:
    radial-gradient(circle at 10% 0%, rgba(14, 165, 233, 0.1), transparent 42%),
    radial-gradient(circle at 90% 100%, rgba(16, 185, 129, 0.1), transparent 40%),
    #f8fafc;
  padding: 1rem 0.85rem 1.25rem;
}

.page-inner {
  max-width: 42rem;
  margin: 0 auto;
}

.eyebrow {
  font-size: 0.7rem;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: #0ea5e9;
  font-weight: 700;
  margin-bottom: 0.35rem;
}

.title {
  font-size: clamp(1.55rem, 5vw, 2.35rem);
  font-weight: 800;
  color: #0f172a;
  letter-spacing: -0.02em;
}

.accent-line {
  width: 3rem;
  height: 3px;
  margin: 0.6rem auto 0;
  border-radius: 999px;
  background: linear-gradient(90deg, #0ea5e9, #10b981);
}

.skill-group {
  margin-top: 0.85rem;
  padding: 0.8rem 0.85rem;
  border-radius: 1rem;
  background: #fff;
  border: 1px solid rgba(226, 232, 240, 0.95);
  box-shadow: 0 10px 28px -20px rgba(15, 23, 42, 0.4);
}

.group-head {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.6rem;
}

.group-dot {
  width: 0.55rem;
  height: 0.55rem;
  border-radius: 999px;
  flex-shrink: 0;
}

.group-head h3 {
  font-size: 0.78rem;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: #475569;
}

.chips {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
}

.chip {
  display: inline-flex;
  align-items: center;
  padding: 0.35rem 0.65rem;
  border-radius: 999px;
  font-size: 0.72rem;
  font-weight: 600;
  color: #0f172a;
  background: color-mix(in srgb, var(--accent) 12%, white);
  border: 1px solid color-mix(in srgb, var(--accent) 28%, white);
  transition: transform 0.15s ease, background 0.15s ease;
}

.chip:hover {
  transform: translateY(-1px);
  background: color-mix(in srgb, var(--accent) 18%, white);
}

@media (min-width: 640px) {
  .page-shell {
    padding: 1.25rem 1.15rem;
  }

  .skill-group {
    padding: 0.95rem 1rem;
  }

  .chip {
    font-size: 0.78rem;
    padding: 0.4rem 0.75rem;
  }
}
</style>
