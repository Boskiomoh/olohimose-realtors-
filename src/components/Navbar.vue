<template>
  <header class="header-wrapper">
    <nav class="navbar">
      <div class="logo">
        <img :src="logo" alt="Olohimose Realtors Logo" />
      </div>
      <div class="menu" :class="{ active: isNavOpen }">
        <a href="#home" @click="closeNav" class="nav-link">Home</a>
        <a href="#about" @click="closeNav" class="nav-link">About</a>
        <a href="#services" @click="closeNav" class="nav-link">Services</a>
        <a href="#contact" @click="closeNav" class="nav-link">Contact</a>
      </div>
      <button class="nav-toggle" @click="toggleNav" :class="{ active: isNavOpen }">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </button>
    </nav>
  </header>
</template>

<script>
import Logo from "../assets/logo.png";

export default {
  name: "Navbar",
  data() {
    return {
      isNavOpen: false,
      logo: Logo,
    };
  },
  methods: {
    toggleNav() {
      this.isNavOpen = !this.isNavOpen;
    },
    closeNav() {
      this.isNavOpen = false;
    }
  },
  mounted() {
    // Close mobile menu when clicking outside
    document.addEventListener('click', (e) => {
      if (!this.$el.contains(e.target)) {
        this.isNavOpen = false;
      }
    });
  }
};
</script>

<style scoped>
.header-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: rgba(11, 30, 54, 0.95);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.logo img {
  height: 60px;
  width: auto;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.logo img:hover {
  transform: scale(1.05);
}

.menu {
  display: flex;
  gap: 2.5rem;
  align-items: center;
}

.nav-link {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  font-size: 1rem;
  position: relative;
  padding: 0.5rem 0;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.nav-link::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: #c9a15e;
}

.nav-link:hover::before {
  width: 100%;
}

.nav-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.nav-toggle:hover {
  background: rgba(255, 255, 255, 0.1);
}

.nav-toggle .bar {
  width: 25px;
  height: 3px;
  margin: 4px 0;
  background-color: #fff;
  transition: all 0.3s ease;
  border-radius: 2px;
}

.nav-toggle.active .bar:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.nav-toggle.active .bar:nth-child(2) {
  opacity: 0;
}

.nav-toggle.active .bar:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

@media (max-width: 768px) {
  .navbar {
    padding: 1rem;
  }
  
  .logo img {
    height: 50px;
  }
  
  .menu {
    flex-direction: column;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: rgba(11, 30, 54, 0.98);
    backdrop-filter: blur(20px);
    max-height: 0;
    overflow: hidden;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    gap: 0;
  }
  
  .menu.active {
    max-height: 300px;
    padding: 2rem 0;
  }
  
  .nav-link {
    padding: 1rem 2rem;
    width: 100%;
    text-align: center;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  }
  
  .nav-link:last-child {
    border-bottom: none;
  }
  
  .nav-toggle {
    display: block;
  }
}

/* Smooth scroll behavior */
html {
  scroll-behavior: smooth;
}

/* Add padding to body to account for fixed header */
body {
  padding-top: 80px;
}

@media (max-width: 768px) {
  body {
    padding-top: 70px;
  }
}
</style>