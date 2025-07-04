<template>
  <section id="home" class="hero">
    <!-- Background Image Carousel -->
    <transition name="fade">
      <div
        v-if="images.length"
        :key="currentIndex"
        class="hero-bg"
        :style="{ backgroundImage: 'url(' + images[currentIndex] + ')' }"
      ></div>
    </transition>
    <!-- Gradient Overlay for Enhanced Readability -->
    <div class="hero-overlay"></div>
    <!-- Text Overlay -->
    <div class="hero-content">
      <div class="hero-badge">
        <span>Premium Real Estate Services</span>
      </div>
      <h1>Find Your Perfect Home in Abuja</h1>
      <p>
        Olohimose Realtors delivers exceptional property management and investment consulting services. 
        We transform your real estate dreams into reality with personalized attention and expert guidance.
      </p>
      <div class="hero-actions">
        <button class="cta-primary" @click="scrollToContact">Get Started</button>
        <button class="cta-secondary" @click="scrollToServices">Our Services</button>
      </div>
      <div class="hero-stats">
        <div class="stat">
          <span class="stat-number">500+</span>
          <span class="stat-label">Properties Managed</span>
        </div>
        <div class="stat">
          <span class="stat-number">15+</span>
          <span class="stat-label">Years Experience</span>
        </div>
        <div class="stat">
          <span class="stat-number">98%</span>
          <span class="stat-label">Client Satisfaction</span>
        </div>
      </div>
    </div>
    <!-- Scroll Indicator -->
    <div class="scroll-indicator" @click="scrollToAbout">
      <div class="scroll-arrow"></div>
    </div>
  </section>
</template>

<script>
import heroBg1 from "../assets/heroBg1.jpg";
import heroBg3 from "../assets/heroBg3.jpg";
import heroBg4 from "../assets/heroBg4.jpg";
import heroBg9 from "../assets/heroBg9.jpg";
import heroBg11 from "../assets/heroBg11.jpg";

export default {
  name: "Hero",
  data() {
    return {
      images: [heroBg1, heroBg3, heroBg4, heroBg9, heroBg11],
      currentIndex: 0,
      interval: null,
    };
  },
  mounted() {
    this.startCarousel();
  },
  beforeUnmount() {
    clearInterval(this.interval);
  },
  methods: {
    startCarousel() {
      this.interval = setInterval(() => {
        this.currentIndex = (this.currentIndex + 1) % this.images.length;
      }, 6000);
    },
    scrollToContact() {
      document.getElementById('contact').scrollIntoView({ behavior: 'smooth' });
    },
    scrollToServices() {
      document.getElementById('services').scrollIntoView({ behavior: 'smooth' });
    },
    scrollToAbout() {
      document.getElementById('about').scrollIntoView({ behavior: 'smooth' });
    }
  },
};
</script>

<style scoped>
.hero {
  position: relative;
  height: 100vh;
  overflow: hidden;
  background-color: #0b1e36;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 2rem;
  color: #fff;
}

.hero-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  z-index: 1;
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    135deg,
    rgba(11, 30, 54, 0.85) 0%,
    rgba(201, 161, 94, 0.15) 50%,
    rgba(11, 30, 54, 0.9) 100%
  );
  z-index: 2;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1.5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.hero-content {
  position: relative;
  z-index: 3;
  max-width: 900px;
  padding: 2rem;
  animation: fadeInUp 1.2s ease-out;
}

.hero-badge {
  display: inline-block;
  background: rgba(201, 161, 94, 0.2);
  border: 1px solid rgba(201, 161, 94, 0.4);
  padding: 0.5rem 1.5rem;
  border-radius: 50px;
  margin-bottom: 2rem;
  backdrop-filter: blur(10px);
  animation: fadeInUp 1.2s ease-out 0.2s both;
}

.hero-badge span {
  color: #c9a15e;
  font-size: 0.9rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.hero-content h1 {
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 1.5rem;
  text-shadow: 0 4px 20px rgba(0, 0, 0, 0.6);
  line-height: 1.2;
  background: linear-gradient(135deg, #ffffff 0%, #f0f0f0 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: fadeInUp 1.2s ease-out 0.4s both;
}

.hero-content p {
  font-size: 1.3rem;
  line-height: 1.7;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
  margin-bottom: 3rem;
  opacity: 0.95;
  animation: fadeInUp 1.2s ease-out 0.6s both;
}

.hero-actions {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  margin-bottom: 4rem;
  animation: fadeInUp 1.2s ease-out 0.8s both;
}

.cta-primary, .cta-secondary {
  padding: 1rem 2.5rem;
  border-radius: 50px;
  font-size: 1.1rem;
  font-weight: 600;
  border: none;
  cursor: pointer;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  text-transform: uppercase;
  letter-spacing: 0.5px;
  position: relative;
  overflow: hidden;
}

.cta-primary {
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  color: #fff;
  box-shadow: 0 8px 25px rgba(201, 161, 94, 0.4);
}

.cta-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 35px rgba(201, 161, 94, 0.6);
  background: linear-gradient(135deg, #d4ac6a 0%, #c9a15e 100%);
}

.cta-secondary {
  background: transparent;
  color: #fff;
  border: 2px solid rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.cta-secondary:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(255, 255, 255, 0.6);
  transform: translateY(-3px);
}

.hero-stats {
  display: flex;
  justify-content: center;
  gap: 4rem;
  animation: fadeInUp 1.2s ease-out 1s both;
}

.stat {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2.5rem;
  font-weight: 800;
  color: #c9a15e;
  margin-bottom: 0.5rem;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
}

.stat-label {
  font-size: 0.9rem;
  opacity: 0.8;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  cursor: pointer;
  z-index: 3;
  animation: bounce 2s infinite;
}

.scroll-arrow {
  width: 24px;
  height: 24px;
  border-right: 2px solid rgba(255, 255, 255, 0.7);
  border-bottom: 2px solid rgba(255, 255, 255, 0.7);
  transform: rotate(45deg);
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateX(-50%) translateY(0);
  }
  40% {
    transform: translateX(-50%) translateY(-10px);
  }
  60% {
    transform: translateX(-50%) translateY(-5px);
  }
}

@media (max-width: 768px) {
  .hero-content h1 {
    font-size: 2.5rem;
  }
  .hero-content p {
    font-size: 1.1rem;
  }
  .hero-actions {
    flex-direction: column;
    align-items: center;
  }
  .hero-stats {
    gap: 2rem;
  }
  .stat-number {
    font-size: 2rem;
  }
}
</style>