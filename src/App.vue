<template>
  <div id="app">
    <Navbar />
    <Hero />
    <AboutUsSections />
    <ServicesSection />
    <ContactSection />
    <FooterSection />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import AboutUsSections from './components/AboutUsSections.vue'
import ServicesSection from './components/ServicesSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Hero,
    AboutUsSections,
    ServicesSection,
    ContactSection,
    FooterSection
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  line-height: 1.6;
  color: #333;
  scroll-behavior: smooth;
  padding-top: 80px;
}

html {
  scroll-behavior: smooth;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(135deg, #b8935a 0%, #a8844f 100%);
}

/* Selection color */
::selection {
  background: rgba(201, 161, 94, 0.3);
  color: #0b1e36;
}

/* Focus styles for accessibility */
button:focus,
input:focus,
textarea:focus,
select:focus {
  outline: 2px solid #c9a15e;
  outline-offset: 2px;
}

/* Smooth transitions for all interactive elements */
a, button, input, textarea, select {
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  body {
    padding-top: 70px;
  }
}
</style>