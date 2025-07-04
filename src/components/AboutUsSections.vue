<template>
  <section id="about" class="about-sections">
    <div class="container">
      <div class="section-header">
        <span class="section-badge">Why Choose Us</span>
        <h2>Built on Trust & Excellence</h2>
      </div>
      
      <div class="about-grid">
        <div class="about-card experience">
          <div class="card-background"></div>
          <div class="icon-container">
            <div class="icon-wrapper">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
              </svg>
            </div>
          </div>
          <div class="content">
            <h3>Proven Experience</h3>
            <p>
              Over 15 years of excellence in Abuja's real estate market. Our track record speaks for itself with 
              hundreds of satisfied clients and successful property transactions across the FCT.
            </p>
            <div class="highlight-stats">
              <div class="stat">
                <span class="number">500+</span>
                <span class="label">Properties Managed</span>
              </div>
              <div class="stat">
                <span class="number">15+</span>
                <span class="label">Years Experience</span>
              </div>
            </div>
          </div>
        </div>

        <div class="about-card mission">
          <div class="card-background"></div>
          <div class="icon-container">
            <div class="icon-wrapper">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M22 12h-4l-3 9L9 3l-3 9H2"/>
              </svg>
            </div>
          </div>
          <div class="content">
            <h3>Our Mission</h3>
            <p>
              To revolutionize real estate services in Nigeria by delivering world-class property management 
              and investment solutions that exceed client expectations and build lasting relationships.
            </p>
            <div class="mission-points">
              <div class="point">
                <span class="point-icon">🎯</span>
                <span>Client-First Approach</span>
              </div>
              <div class="point">
                <span class="point-icon">🏆</span>
                <span>Excellence in Service</span>
              </div>
              <div class="point">
                <span class="point-icon">🤝</span>
                <span>Trusted Partnerships</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AboutUsSections",
};
</script>

<style scoped>
.about-sections {
  padding: 8rem 2rem;
  background: linear-gradient(135deg, #0b1e36 0%, #1a2f4a 100%);
  color: #fff;
  position: relative;
  overflow: hidden;
}

.about-sections::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="rgba(255,255,255,0.02)"/><circle cx="75" cy="75" r="1" fill="rgba(255,255,255,0.02)"/><circle cx="50" cy="10" r="0.5" fill="rgba(255,255,255,0.01)"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
  opacity: 0.3;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
}

.section-header {
  text-align: center;
  margin-bottom: 5rem;
}

.section-badge {
  display: inline-block;
  background: rgba(201, 161, 94, 0.2);
  border: 1px solid rgba(201, 161, 94, 0.4);
  color: #c9a15e;
  padding: 0.5rem 1.5rem;
  border-radius: 50px;
  font-size: 0.9rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 1.5rem;
  backdrop-filter: blur(10px);
}

.section-header h2 {
  font-size: 3rem;
  font-weight: 800;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  background: linear-gradient(135deg, #ffffff 0%, #c9a15e 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
  gap: 3rem;
}

.about-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 24px;
  padding: 3rem;
  position: relative;
  overflow: hidden;
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.about-card:hover {
  transform: translateY(-8px);
  background: rgba(255, 255, 255, 0.08);
  border-color: rgba(201, 161, 94, 0.3);
}

.card-background {
  position: absolute;
  top: -50%;
  right: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(201, 161, 94, 0.1) 0%, transparent 70%);
  opacity: 0;
  transition: opacity 0.6s ease;
}

.about-card:hover .card-background {
  opacity: 1;
}

.icon-container {
  margin-bottom: 2rem;
}

.icon-wrapper {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  box-shadow: 0 8px 25px rgba(201, 161, 94, 0.4);
}

.icon-wrapper svg {
  width: 40px;
  height: 40px;
}

.content h3 {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: #fff;
}

.content p {
  font-size: 1.1rem;
  line-height: 1.8;
  color: rgba(255, 255, 255, 0.9);
  margin-bottom: 2rem;
}

.highlight-stats {
  display: flex;
  gap: 2rem;
}

.stat {
  text-align: center;
}

.stat .number {
  display: block;
  font-size: 2rem;
  font-weight: 800;
  color: #c9a15e;
  margin-bottom: 0.5rem;
}

.stat .label {
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.7);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.mission-points {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.point {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  transition: all 0.3s ease;
}

.point:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateX(8px);
}

.point-icon {
  font-size: 1.5rem;
}

@media (max-width: 768px) {
  .about-sections {
    padding: 4rem 1rem;
  }
  
  .section-header h2 {
    font-size: 2.2rem;
  }
  
  .about-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .about-card {
    padding: 2rem;
  }
  
  .highlight-stats {
    justify-content: center;
  }
}
</style>