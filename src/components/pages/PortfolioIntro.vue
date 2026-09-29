<template>
  <div class="intro-page">
    <div class="intro-inner">
      <div class="photo-wrap">
        <img
          :src="profileImg"
          alt="Mubashir Hussain"
          class="photo"
        />
      </div>

      <h1 class="title">PORTFOLIO</h1>
      <p class="by">by</p>
      <h2 class="name">Mubashir Hussain</h2>
      <p class="role">Software Engineer · 3+ Years</p>
    </div>
  </div>
</template>

<script setup>
import profileImg from '@/assets/images/profile.png'
</script>

<style scoped>
.intro-page {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 1rem 0.85rem;
  background:
    radial-gradient(circle at 50% 20%, rgba(14, 165, 233, 0.12), transparent 45%),
    linear-gradient(160deg, #f8fafc 0%, #e2e8f0 100%);
}

.intro-inner {
  width: 100%;
  max-width: 22rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Circle crop + zoom so subject doesn't look far away */
.photo-wrap {
  width: clamp(7.5rem, 28vw, 10.5rem);
  height: clamp(7.5rem, 28vw, 10.5rem);
  border-radius: 50%;
  overflow: hidden;
  margin-bottom: 1.1rem;
  border: 3px solid #fff;
  box-shadow:
    0 12px 28px -10px rgba(15, 23, 42, 0.35),
    0 0 0 1px rgba(148, 163, 184, 0.35);
  background: #cbd5e1;
}

.photo {
  width: 100%;
  height: 100%;
  display: block;
  /* Zoom in + shift up to face/upper body */
  object-fit: cover;
  object-position: 50% 18%;
  transform: scale(1.55);
  transform-origin: 65% 88%;
}

.title {
  font-size: clamp(1.75rem, 6vw, 2.75rem);
  font-weight: 900;
  color: #0f172a;
  letter-spacing: 0.04em;
  line-height: 1.1;
}

.by {
  margin-top: 0.45rem;
  font-size: clamp(1rem, 3.5vw, 1.35rem);
  font-weight: 500;
  color: #64748b;
}

.name {
  margin-top: 0.35rem;
  font-size: clamp(1.35rem, 5vw, 2.1rem);
  font-weight: 800;
  color: #0f172a;
}

.role {
  margin-top: 0.55rem;
  font-size: clamp(0.85rem, 2.8vw, 1.05rem);
  color: #475569;
  font-weight: 500;
}

@media (min-width: 768px) {
  .photo-wrap {
    width: 11rem;
    height: 11rem;
    margin-bottom: 1.35rem;
  }
}
</style>
