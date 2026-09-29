<template>
  <div class="page-shell">
    <div class="page-inner">
      <header class="text-center mb-5 sm:mb-6">
        <p class="eyebrow">Get to know me</p>
        <h2 class="title">About Me</h2>
        <div class="accent-line"></div>
      </header>

      <div class="intro-card">
        <p>
          Experienced <strong>Full Stack Developer</strong> specializing in
          <strong>Laravel, Vue.js, React &amp; Python</strong>.
          Building scalable ERP, multi-tenant booking, CRM, claim platforms, and realtime
          chat/call systems with complex 3rd-party API integrations.
        </p>
      </div>

      <div class="contact-list">
        <a href="mailto:mh2603391@gmail.com" class="contact-row">
          <span class="contact-icon email">
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"/><path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"/></svg>
          </span>
          <span class="contact-meta">
            <span class="label">Email</span>
            <span class="value">mh2603391@gmail.com</span>
          </span>
        </a>

        <a href="tel:+923480464778" class="contact-row">
          <span class="contact-icon phone">
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z"/></svg>
          </span>
          <span class="contact-meta">
            <span class="label">Phone</span>
            <span class="value">+923480464778</span>
          </span>
        </a>

        <div class="contact-row static">
          <span class="contact-icon location">
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd"/></svg>
          </span>
          <span class="contact-meta">
            <span class="label">Location</span>
            <span class="value">Firdous Market, Lahore</span>
          </span>
        </div>

        <a href="https://github.com/mubashir206" target="_blank" rel="noopener noreferrer" class="contact-row">
          <span class="contact-icon github">
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
          </span>
          <span class="contact-meta">
            <span class="label">GitHub</span>
            <span class="value">mubashir206</span>
          </span>
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.page-shell {
  height: 100%;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
  background:
    radial-gradient(circle at top right, rgba(14, 165, 233, 0.12), transparent 40%),
    radial-gradient(circle at bottom left, rgba(16, 185, 129, 0.1), transparent 35%),
    linear-gradient(180deg, #f8fafc 0%, #f1f5f9 100%);
  padding: 1rem 0.85rem 1.25rem;
}

.page-inner {
  max-width: 40rem;
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
  font-size: clamp(1.6rem, 5vw, 2.4rem);
  font-weight: 800;
  color: #0f172a;
  letter-spacing: -0.02em;
}

.accent-line {
  width: 3rem;
  height: 3px;
  margin: 0.65rem auto 0;
  border-radius: 999px;
  background: linear-gradient(90deg, #0ea5e9, #10b981);
}

.intro-card {
  margin-top: 1.1rem;
  padding: 0.95rem 1rem;
  border-radius: 1rem;
  background: rgba(255, 255, 255, 0.92);
  border: 1px solid rgba(148, 163, 184, 0.35);
  box-shadow: 0 10px 30px -18px rgba(15, 23, 42, 0.35);
}

.intro-card p {
  font-size: 0.88rem;
  line-height: 1.55;
  color: #334155;
  text-align: center;
}

.intro-card strong {
  color: #0f172a;
  font-weight: 700;
}

.contact-list {
  margin-top: 0.9rem;
  display: grid;
  gap: 0.55rem;
}

.contact-row {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.7rem 0.8rem;
  border-radius: 0.9rem;
  background: #fff;
  border: 1px solid rgba(226, 232, 240, 0.95);
  box-shadow: 0 6px 18px -14px rgba(15, 23, 42, 0.35);
  text-decoration: none;
  transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
}

.contact-row:not(.static):hover {
  transform: translateY(-1px);
  border-color: rgba(14, 165, 233, 0.45);
  box-shadow: 0 12px 24px -16px rgba(14, 165, 233, 0.55);
}

.contact-icon {
  width: 2.1rem;
  height: 2.1rem;
  border-radius: 0.65rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  flex-shrink: 0;
}

.contact-icon.email { background: linear-gradient(135deg, #0ea5e9, #0284c7); }
.contact-icon.phone { background: linear-gradient(135deg, #10b981, #059669); }
.contact-icon.location { background: linear-gradient(135deg, #f59e0b, #d97706); }
.contact-icon.github { background: linear-gradient(135deg, #334155, #0f172a); }

.contact-meta {
  display: flex;
  flex-direction: column;
  min-width: 0;
}

.label {
  font-size: 0.65rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #64748b;
  font-weight: 600;
}

.value {
  font-size: 0.85rem;
  color: #0f172a;
  font-weight: 600;
  word-break: break-word;
}

@media (min-width: 640px) {
  .page-shell {
    padding: 1.4rem 1.25rem;
  }

  .contact-list {
    grid-template-columns: 1fr 1fr;
  }

  .intro-card p {
    font-size: 0.98rem;
  }
}
</style>
