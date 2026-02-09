<template>
  <div class="book-wrapper">
    <!-- Beautiful Background -->
    <div class="background-container">
      <div class="bg-pattern"></div>
      <div class="bg-overlay"></div>
    </div>

    <!-- Closed Book - Real Book Look -->
    <transition name="book-cover-slide">
      <div 
        v-if="!isBookOpen"
        class="closed-book-wrapper"
        :key="'closed-book'"
      >
        <div class="real-closed-book" @click="openBook">
          <!-- Book Spine (Left Edge) -->
          <div class="book-spine-edge"></div>
          
          <!-- Book Cover (Front) - CLOSED STATE -->
          <div class="book-front-cover closed-cover">
            <div class="cover-design">
              <div class="cover-ornament-top"></div>
              <h1 class="cover-title">Portfolio</h1>
              <div class="cover-divider"></div>
              <h2 class="cover-author">Mubashir Hussain</h2>
              <p class="cover-subtitle">Software Engineer</p>
              <div class="cover-ornament-bottom"></div>
              <div class="click-to-open">
                <span class="pulse-dot"></span>
                Click to Open
              </div>
            </div>
          </div>
          
          <!-- Book Pages Edge (Right) -->
          <div class="book-pages-right-edge"></div>
        </div>
      </div>
    </transition>

    <!-- Book Container (After Opening - Full Width) -->
    <transition name="book-pages-reveal">
      <div 
        v-if="isBookOpen"
        class="book-container book-pages-active"
        :key="'open-book'"
      >
      <div class="book-3d">
        <div class="book-inner">
          
          <!-- All Pages Stack (Background) -->
          <div class="pages-stack">
            <div class="stack-page" v-for="i in 3" :key="i" :style="{ transform: `translateZ(-${i * 3}px)`, opacity: 1 - (i * 0.15) }"></div>
          </div>

          <!-- Left Page (Clickable) -->
          <div 
            class="book-page left-page"
            :class="{ 'clickable': canGoPrev }"
            @click="handleLeftPageClick"
          >
            <div class="page-content">
              <component :is="leftPageComponent" :key="'left-' + currentPageIndex" v-if="leftPageComponent" />
            </div>
          </div>

          <!-- Center Spine -->
          <div class="book-spine"></div>

          <!-- Right Page (Current) - Clickable to flip -->
          <div 
            class="book-page right-page"
            :class="{ 
              'flipping-forward': isFlipping && direction === 'forward',
              'flipping-backward': isFlipping && direction === 'backward',
              'clickable': canGoNext 
            }"
            @click="handleRightPageClick"
          >
            <!-- Front Side (Current Right Page) -->
            <div class="page-side front-side">
              <div class="page-content">
                <component :is="currentPageComponent" :key="'current-' + currentPageIndex" />
              </div>
            </div>
            
            <!-- Back Side (Next Left Page - shown when flipping) -->
            <div class="page-side back-side">
              <div class="page-content">
                <component :is="nextPageComponent" :key="'next-' + currentPageIndex" v-if="nextPageComponent" />
              </div>
            </div>
          </div>

          <!-- Hidden Next Right Page (Will become right page after flip) -->
          <div class="book-page hidden-next" v-if="currentPageIndex + 3 < totalPages">
            <div class="page-content">
              <component :is="pages[currentPageIndex + 3]" :key="'hidden-' + currentPageIndex" />
            </div>
          </div>

        </div>
      </div>

      <!-- Page Indicator -->
      <div class="page-indicator">
        <div v-for="(page, index) in Math.ceil(totalPages / 2)" :key="index" 
             :class="['dot', { active: Math.floor(currentPageIndex / 2) === index }]"
             @click="goToPage(index * 2)"
        ></div>
      </div>

      <!-- Page Counter -->
      <div class="page-counter">
        {{ currentPageIndex + 1 }}-{{ Math.min(currentPageIndex + 2, totalPages) }} / {{ totalPages }}
      </div>

      <!-- Click Hint -->
      <div class="click-hint" v-if="currentPageIndex === 0">
        <div class="hint-text">
          ← Click pages to navigate →
        </div>
      </div>

      <!-- Close Book Hint on Last Page -->
      <div class="click-hint" v-if="isLastPage">
        <div class="hint-text close-hint">
          Click to Close Book 📕
        </div>
      </div>
      </div>
    </transition>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
import PortfolioIntro from './pages/PortfolioIntro.vue'
import CoverPage from './pages/CoverPage.vue'
import AboutPage from './pages/AboutPage.vue'
import CompetenciesPage from './pages/CompetenciesPage.vue'
import ExperiencePage from './pages/ExperiencePage.vue'
import ProjectsPage1 from './pages/ProjectsPage1.vue'
import ProjectsPage2 from './pages/ProjectsPage2.vue'
import EducationPage from './pages/EducationPage.vue'
import BackCoverPage from './pages/BackCoverPage.vue'

const pages = [
  PortfolioIntro, // Left intro page
  CoverPage,
  AboutPage,
  CompetenciesPage,
  ExperiencePage,
  ProjectsPage1,
  ProjectsPage2,
  EducationPage,
  BackCoverPage
]

const currentPageIndex = ref(0) // Start at index 0 (shows intro on left, cover on right)
const totalPages = pages.length
const isFlipping = ref(false)
const direction = ref('forward') // Track flip direction
const isBookOpen = ref(false) // Book starts closed

const leftPageComponent = computed(() => {
  const leftIndex = currentPageIndex.value
  return pages[leftIndex] || null
})

const currentPageComponent = computed(() => {
  const rightIndex = currentPageIndex.value + 1
  return pages[rightIndex] || pages[currentPageIndex.value]
})

const nextPageComponent = computed(() => {
  const nextLeftIndex = currentPageIndex.value + 2
  return pages[nextLeftIndex] || null
})

const canGoNext = computed(() => currentPageIndex.value < totalPages - 2)
const canGoPrev = computed(() => currentPageIndex.value > 0)
const isLastPage = computed(() => currentPageIndex.value >= totalPages - 2)

const nextPage = () => {
  if (canGoNext.value && !isFlipping.value) {
    direction.value = 'forward'
    isFlipping.value = true
    setTimeout(() => {
      currentPageIndex.value += 2
      isFlipping.value = false
    }, 700)
  }
}

const previousPage = () => {
  if (canGoPrev.value && !isFlipping.value) {
    direction.value = 'backward'
    isFlipping.value = true
    setTimeout(() => {
      currentPageIndex.value -= 2
      isFlipping.value = false
    }, 700)
  }
}

const handleRightPageClick = () => {
  if (canGoNext.value) {
    nextPage()
  } else if (isLastPage.value) {
    // Close the book when on last page
    closeBook()
  }
}

const handleLeftPageClick = () => {
  if (canGoPrev.value) {
    previousPage()
  }
}

const goToPage = (page) => {
  if (!isFlipping.value) {
    direction.value = page > currentPageIndex.value ? 'forward' : 'backward'
    isFlipping.value = true
    setTimeout(() => {
      currentPageIndex.value = page
      isFlipping.value = false
    }, 700)
  }
}

// Open book function - keeps current page state
const openBook = () => {
  if (!isBookOpen.value) {
    isBookOpen.value = true
    // Don't reset page - continue from where it was closed
  }
}

// Close book function - preserves current page
const closeBook = () => {
  if (isBookOpen.value) {
    // Don't reset page - keep current position for next open
    isBookOpen.value = false
  }
}

// Keyboard navigation
const handleKeyPress = (event) => {
  if (!isBookOpen.value) return // Don't navigate if book is closed
  
  if (event.key === 'ArrowRight' || event.key === 'ArrowDown') {
    nextPage()
  } else if (event.key === 'ArrowLeft' || event.key === 'ArrowUp') {
    previousPage()
  }
}

onMounted(() => {
  window.addEventListener('keydown', handleKeyPress)
})

onUnmounted(() => {
  window.removeEventListener('keydown', handleKeyPress)
})
</script>

<style scoped>
/* Main Wrapper */
.book-wrapper {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Closed Book Wrapper - Real Book 3D */
.closed-book-wrapper {
  position: relative;
  width: 90vw;
  max-width: 1600px;
  height: 85vh;
  max-height: 900px;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 10;
  cursor: pointer;
  perspective: 2000px;
}

/* Real Closed Book Structure */
.real-closed-book {
  position: relative;
  width: 55%;
  height: 100%;
  display: flex;
  transform-style: preserve-3d;
  transform: rotateY(-15deg);
  transition: transform 0.4s ease;
}

.real-closed-book:hover {
  transform: rotateY(-10deg) translateY(-10px);
}

/* Book Spine (Left Edge) */
.book-spine-edge {
  width: 60px;
  height: 100%;
  background: linear-gradient(to right,
    #0f172a 0%,
    #1e293b 30%,
    #334155 70%,
    #475569 100%
  );
  border-radius: 15px 0 0 15px;
  box-shadow: 
    -5px 0 20px rgba(0, 0, 0, 0.6),
    inset 10px 0 30px rgba(0, 0, 0, 0.4);
  position: relative;
  z-index: 1;
}

.book-spine-edge::after {
  content: 'PORTFOLIO';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(-90deg);
  color: rgba(255, 255, 255, 0.5);
  font-size: 1.2rem;
  font-weight: 700;
  letter-spacing: 0.3em;
  white-space: nowrap;
}

/* Book Front Cover */
.book-front-cover {
  flex: 1;
  height: 100%;
  background: linear-gradient(145deg, 
    rgba(30, 41, 59, 0.98) 0%, 
    rgba(51, 65, 85, 0.95) 40%,
    rgba(71, 85, 105, 0.98) 100%
  );
  border-radius: 0 15px 15px 0;
  box-shadow: 
    20px 30px 80px rgba(0, 0, 0, 0.6),
    inset 0 0 100px rgba(100, 116, 139, 0.1),
    inset -5px 0 25px rgba(255, 255, 255, 0.05);
  position: relative;
  z-index: 2;
  overflow: hidden;
}

.book-front-cover::before {
  content: '';
  position: absolute;
  inset: 0;
  background: 
    radial-gradient(circle at 30% 30%, rgba(139, 92, 246, 0.15) 0%, transparent 50%),
    radial-gradient(circle at 70% 70%, rgba(59, 130, 246, 0.15) 0%, transparent 50%);
  pointer-events: none;
}

.book-front-cover::after {
  content: '';
  position: absolute;
  top: 20px;
  right: 20px;
  bottom: 20px;
  left: 20px;
  border: 2px solid rgba(148, 163, 184, 0.2);
  border-radius: 10px;
  pointer-events: none;
}

/* Book Pages Edge (Right Side) */
.book-pages-right-edge {
  position: absolute;
  right: -3px;
  top: 15px;
  width: 12px;
  height: calc(100% - 30px);
  background: repeating-linear-gradient(
    to bottom,
    #ffffff 0px,
    #f8f9fa 1px,
    #e9ecef 2px,
    #ffffff 3px
  );
  border-radius: 0 12px 12px 0;
  box-shadow: 
    3px 0 8px rgba(0, 0, 0, 0.3),
    inset -1px 0 3px rgba(0, 0, 0, 0.2);
  z-index: 3;
}

/* Cover Design Content */
.cover-design {
  position: relative;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 4rem;
  z-index: 1;
}

.cover-ornament-top,
.cover-ornament-bottom {
  width: 80%;
  height: 2px;
  background: linear-gradient(to right, 
    transparent, 
    rgba(148, 163, 184, 0.5), 
    transparent
  );
  margin: 1rem 0;
}

.cover-title {
  font-size: 3.5rem;
  font-weight: 800;
  background: linear-gradient(135deg, 
    #f8fafc 0%, 
    #cbd5e1 50%, 
    #94a3b8 100%
  );
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-align: center;
  letter-spacing: 0.1em;
  text-shadow: 0 4px 20px rgba(148, 163, 184, 0.3);
  margin: 1rem 0;
}

.cover-divider {
  width: 60%;
  height: 3px;
  background: linear-gradient(to right, 
    transparent, 
    rgba(139, 92, 246, 0.6), 
    rgba(59, 130, 246, 0.6),
    transparent
  );
  margin: 1.5rem 0;
  box-shadow: 0 0 20px rgba(139, 92, 246, 0.4);
}

.cover-author {
  font-size: 2rem;
  font-weight: 600;
  color: #e2e8f0;
  text-align: center;
  letter-spacing: 0.05em;
  margin: 0.5rem 0;
}

.cover-subtitle {
  font-size: 1.1rem;
  color: #94a3b8;
  text-align: center;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  margin-top: 0.5rem;
}

.click-to-open {
  position: absolute;
  bottom: 2rem;
  font-size: 0.9rem;
  color: #cbd5e1;
  text-align: center;
  animation: pulseText 2s ease-in-out infinite;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.pulse-dot {
  display: inline-block;
  width: 8px;
  height: 8px;
  background: #8b5cf6;
  border-radius: 50%;
  animation: pulseDot 2s ease-in-out infinite;
  box-shadow: 0 0 10px rgba(139, 92, 246, 0.8);
}

@keyframes pulseText {
  0%, 100% {
    opacity: 0.6;
    transform: translateY(0);
  }
  50% {
    opacity: 1;
    transform: translateY(-5px);
  }
}

@keyframes pulseDot {
  0%, 100% {
    transform: scale(1);
    box-shadow: 0 0 10px rgba(139, 92, 246, 0.8);
  }
  50% {
    transform: scale(1.3);
    box-shadow: 0 0 20px rgba(139, 92, 246, 1);
  }
}

.book-shadow {
  position: absolute;
  bottom: -30px;
  left: 50%;
  transform: translateX(-50%);
  width: 90%;
  height: 30px;
  background: radial-gradient(ellipse at center, 
    rgba(0, 0, 0, 0.4) 0%, 
    transparent 70%
  );
  filter: blur(10px);
  animation: shadowPulse 3s ease-in-out infinite;
}

@keyframes shadowPulse {
  0%, 100% {
    opacity: 0.6;
    transform: translateX(-50%) scale(1);
  }
  50% {
    opacity: 0.8;
    transform: translateX(-50%) scale(1.1);
  }
}

/* Book Pages Opening Animation - Smooth Reveal */
.book-pages-active {
  animation: pagesRevealSmooth 1s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

@keyframes pagesRevealSmooth {
  0% {
    opacity: 0;
    transform: translateX(30%) scale(0.8);
  }
  50% {
    opacity: 0.5;
    transform: translateX(15%) scale(0.9);
  }
  100% {
    opacity: 1;
    transform: translateX(0) scale(1);
  }
}

/* Cover Closed State - Distinct Design */
.closed-cover {
  position: relative;
}

.closed-cover::after {
  content: '';
  position: absolute;
  inset: 15px;
  border: 3px solid rgba(148, 163, 184, 0.3);
  border-radius: 12px;
  pointer-events: none;
}

/* Book Cover Slide Transition - ENTER (Cover appears when closing) */
.book-cover-slide-enter-active {
  animation: coverSlideIn 1s cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes coverSlideIn {
  0% {
    opacity: 0;
    transform: translateX(-40%) rotateY(-30deg) scale(0.7);
  }
  40% {
    opacity: 0.5;
    transform: translateX(-20%) rotateY(-20deg) scale(0.85);
  }
  100% {
    opacity: 1;
    transform: translateX(0) rotateY(-15deg) scale(1);
  }
}

/* Book Cover Slide Transition - LEAVE (Cover disappears when opening) */
.book-cover-slide-leave-active {
  animation: coverSlideOut 0.9s cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes coverSlideOut {
  0% {
    opacity: 1;
    transform: translateX(0) rotateY(-15deg) scale(1);
  }
  50% {
    opacity: 0.6;
    transform: translateX(-15%) rotateY(-25deg) scale(0.9);
  }
  100% {
    opacity: 0;
    transform: translateX(-35%) rotateY(-35deg) scale(0.75);
  }
}

/* Book Pages Reveal Transition - ENTER (Pages appear when opening) */
.book-pages-reveal-enter-active {
  animation: pagesRevealSmooth 1s cubic-bezier(0.4, 0, 0.2, 1);
}

/* Book Pages Reveal Transition - LEAVE (Pages disappear when closing) */
.book-pages-reveal-leave-active {
  animation: pagesHideSmooth 0.9s cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes pagesHideSmooth {
  0% {
    opacity: 1;
    transform: translateX(0) scale(1);
  }
  50% {
    opacity: 0.5;
    transform: translateX(20%) scale(0.9);
  }
  100% {
    opacity: 0;
    transform: translateX(40%) scale(0.75);
  }
}

/* Professional Animated Background with Image */
.background-container {
  position: absolute;
  inset: 0;
  z-index: 0;
  overflow: hidden;
}

.bg-pattern {
  position: absolute;
  inset: 0;
  background-image: url('https://images.unsplash.com/photo-1506704900226-2d5f3e85ffed?w=1920&q=80');
  background-size: cover;
  background-position: center;
  animation: slowPan 40s ease-in-out infinite alternate;
}

@keyframes slowPan {
  0% {
    transform: scale(1.1) translateX(0) translateY(0);
  }
  50% {
    transform: scale(1.15) translateX(-30px) translateY(-20px);
  }
  100% {
    transform: scale(1.1) translateX(30px) translateY(20px);
  }
}

.bg-overlay {
  position: absolute;
  inset: 0;
  background: 
    radial-gradient(circle at 30% 50%, 
      rgba(15, 23, 42, 0.85) 0%, 
      rgba(30, 41, 59, 0.90) 40%, 
      rgba(51, 65, 85, 0.88) 70%,
      rgba(71, 85, 105, 0.85) 100%
    );
  backdrop-filter: blur(0.5px);
}

@keyframes gradientShift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

/* Book Container */
.book-container {
  position: relative;
  z-index: 10;
  width: 90vw;
  max-width: 1600px;
  height: 85vh;
  max-height: 900px;
}

.book-3d {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  perspective: 2500px;
}

.book-inner {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  transform-style: preserve-3d;
}

/* Pages Stack Effect */
.pages-stack {
  position: absolute;
  right: 0;
  top: 0;
  width: 50%;
  height: 100%;
  z-index: 1;
  pointer-events: none;
}

.stack-page {
  position: absolute;
  width: 100%;
  height: 100%;
  background: white;
  border-radius: 0 20px 20px 0;
  box-shadow: -2px 0 10px rgba(0, 0, 0, 0.1);
}

/* Book Pages */
.book-page {
  position: relative;
  width: 50%;
  height: 100%;
  background: white;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  overflow: hidden;
}

/* Left Page */
.left-page {
  border-radius: 20px 0 0 20px;
  border-right: 2px solid rgba(0, 0, 0, 0.1);
}

/* Center Spine */
.book-spine {
  position: absolute;
  left: 50%;
  top: 0;
  bottom: 0;
  width: 40px;
  transform: translateX(-50%);
  background: linear-gradient(to right, 
    rgba(0, 0, 0, 0.15) 0%,
    rgba(0, 0, 0, 0.05) 20%,
    rgba(0, 0, 0, 0.02) 50%,
    rgba(0, 0, 0, 0.05) 80%,
    rgba(0, 0, 0, 0.15) 100%
  );
  z-index: 5;
  pointer-events: none;
}

/* Right Page with Flip */
.right-page {
  border-radius: 0 20px 20px 0;
  transform-origin: left center;
  transform-style: preserve-3d;
  z-index: 10;
  cursor: pointer;
  transition: transform 0.8s cubic-bezier(0.645, 0.045, 0.355, 1);
}

.page-side {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
  background: white;
  overflow: hidden;
}

.front-side {
  transform: rotateY(0deg);
  border-radius: 0 20px 20px 0;
}

.back-side {
  transform: rotateY(180deg);
  border-radius: 0 20px 20px 0;
}

/* Hidden Next Page */
.hidden-next {
  position: absolute;
  right: 0;
  top: 0;
  width: 50%;
  height: 100%;
  border-radius: 0 20px 20px 0;
  z-index: 2;
  pointer-events: none;
}

/* Clickable Pages */
.clickable {
  cursor: pointer;
  transition: transform 0.2s ease;
}

.clickable:hover {
  transform: scale(1.01);
}

.left-page.clickable:hover {
  box-shadow: -5px 0 15px rgba(102, 126, 234, 0.3);
}

.right-page.clickable:hover {
  box-shadow: 5px 0 15px rgba(102, 126, 234, 0.3);
}

/* Ultra Smooth Forward Flip Animation */
.right-page.flipping-forward {
  animation: flipForward 0.7s cubic-bezier(0.34, 0.03, 0.21, 0.99) forwards;
}

@keyframes flipForward {
  0% {
    transform: rotateY(0deg) translateZ(0);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  }
  15% {
    transform: rotateY(-27deg) translateZ(70px);
    box-shadow: -12px 20px 60px rgba(0, 0, 0, 0.32);
  }
  30% {
    transform: rotateY(-54deg) translateZ(90px);
    box-shadow: -24px 20px 75px rgba(0, 0, 0, 0.4);
  }
  50% {
    transform: rotateY(-90deg) translateZ(100px);
    box-shadow: -35px 20px 85px rgba(0, 0, 0, 0.48);
  }
  70% {
    transform: rotateY(-126deg) translateZ(90px);
    box-shadow: -24px 20px 75px rgba(0, 0, 0, 0.4);
  }
  85% {
    transform: rotateY(-153deg) translateZ(70px);
    box-shadow: -12px 20px 60px rgba(0, 0, 0, 0.32);
  }
  100% {
    transform: rotateY(-180deg) translateZ(0);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  }
}

/* Ultra Smooth Backward Flip Animation */
.right-page.flipping-backward {
  animation: flipBackward 0.7s cubic-bezier(0.34, 0.03, 0.21, 0.99) forwards;
}

@keyframes flipBackward {
  0% {
    transform: rotateY(-180deg) translateZ(0);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  }
  15% {
    transform: rotateY(-153deg) translateZ(70px);
    box-shadow: -12px 20px 60px rgba(0, 0, 0, 0.32);
  }
  30% {
    transform: rotateY(-126deg) translateZ(90px);
    box-shadow: -24px 20px 75px rgba(0, 0, 0, 0.4);
  }
  50% {
    transform: rotateY(-90deg) translateZ(100px);
    box-shadow: -35px 20px 85px rgba(0, 0, 0, 0.48);
  }
  70% {
    transform: rotateY(-54deg) translateZ(90px);
    box-shadow: -24px 20px 75px rgba(0, 0, 0, 0.4);
  }
  85% {
    transform: rotateY(-27deg) translateZ(70px);
    box-shadow: -12px 20px 60px rgba(0, 0, 0, 0.32);
  }
  100% {
    transform: rotateY(0deg) translateZ(0);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  }
}

/* Page Content */
.page-content {
  width: 100%;
  height: 100%;
  overflow-y: hidden;
  overflow-x: hidden;
  padding: 20px;
}

/* Enable scroll only for specific pages with lots of content */
.page-content:has(.overflow-y-auto) {
  overflow-y: auto;
}

.back-side .page-content {
  transform: scaleX(-1);
  direction: ltr;
}

/* Page Numbers */
.page-number {
  position: absolute;
  bottom: 30px;
  font-size: 14px;
  color: #999;
  font-weight: 600;
}

.page-number.left {
  left: 30px;
}

.page-number.right {
  right: 30px;
}

/* Page Indicator */
.page-indicator {
  position: absolute;
  bottom: -50px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 12px;
  z-index: 20;
}

.dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.4);
  cursor: pointer;
  transition: all 0.3s ease;
  border: 2px solid rgba(255, 255, 255, 0.6);
}

.dot:hover {
  background: rgba(255, 255, 255, 0.7);
  transform: scale(1.2);
}

.dot.active {
  background: white;
  width: 32px;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(255, 255, 255, 0.5);
}

/* Page Counter */
.page-counter {
  position: absolute;
  bottom: -80px;
  left: 50%;
  transform: translateX(-50%);
  color: white;
  font-size: 18px;
  font-weight: 700;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.4);
  letter-spacing: 1px;
  z-index: 20;
}

/* Click Hint */
.click-hint {
  position: absolute;
  top: -60px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 20;
  animation: fadeInOut 3s ease-in-out infinite;
}

.close-hint {
  background: rgba(239, 68, 68, 0.15) !important;
  border-color: rgba(239, 68, 68, 0.4) !important;
  color: #fca5a5 !important;
}

.hint-text {
  color: white;
  font-size: 16px;
  font-weight: 600;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.4);
  padding: 12px 24px;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 25px;
  border: 2px solid rgba(255, 255, 255, 0.3);
}

@keyframes fadeInOut {
  0%, 100% { opacity: 0.5; }
  50% { opacity: 1; }
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .book-container {
    width: 95%;
    height: 75vh;
  }

  .book-inner {
    flex-direction: column;
  }

  .book-page {
    width: 100%;
    height: 100%;
  }

  .left-page {
    display: none;
  }

  .right-page {
    border-radius: 20px;
  }

  .book-spine {
    display: none;
  }

  .nav-btn {
    width: 60px;
    height: 60px;
  }

  .nav-btn.left {
    left: 15px;
  }

  .nav-btn.right {
    right: 15px;
  }
}

/* Custom Scrollbar */
.page-content::-webkit-scrollbar {
  width: 8px;
}

.page-content::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0.05);
  border-radius: 10px;
  margin: 15px;
}

.page-content::-webkit-scrollbar-thumb {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 10px;
}

.page-content::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(135deg, #764ba2 0%, #667eea 100%);
}
</style>

