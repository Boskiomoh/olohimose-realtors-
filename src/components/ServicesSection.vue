<template>
  <section id="services" class="services-section">
    <div class="container">
      <div class="section-header">
        <span class="section-badge">What We Offer</span>
        <h2>Premium Real Estate Services</h2>
        <p class="section-subtitle">
          Comprehensive solutions tailored to your property needs with exceptional attention to detail
        </p>
      </div>
      <div class="service-cards">
        <div class="service-card" v-for="(service, index) in services" :key="index">
          <div class="service-icon">
            <div class="icon-wrapper" v-html="service.icon"></div>
          </div>
          <div class="service-content">
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
            <ul class="service-features">
              <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
            </ul>
          </div>
          <div class="service-hover-effect"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ServicesSection",
  data() {
    return {
      services: [
        {
          title: "Property Management",
          description: "Comprehensive property management services that maximize your investment returns while minimizing your stress.",
          features: ["24/7 Maintenance Support", "Tenant Screening", "Rent Collection", "Property Inspections"],
          icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                   <path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/>
                   <polyline points="9,22 9,12 15,12 15,22"/>
                 </svg>`
        },
        {
          title: "Investment Consulting",
          description: "Strategic investment advice backed by deep market knowledge and years of experience in Abuja's real estate market.",
          features: ["Market Analysis", "ROI Projections", "Portfolio Optimization", "Risk Assessment"],
          icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                   <line x1="12" y1="1" x2="12" y2="23"/>
                   <path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/>
                 </svg>`
        },
        {
          title: "Property Marketing",
          description: "Professional marketing strategies that showcase your properties to qualified buyers and tenants effectively.",
          features: ["Professional Photography", "Digital Marketing", "Market Positioning", "Lead Generation"],
          icon: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                   <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/>
                   <path d="M13 8l-3 3 3 3"/>
                 </svg>`
        }
      ]
    };
  }
};
</script>

<style scoped>
.services-section {
  padding: 8rem 2rem;
  background: linear-gradient(135deg, #f8f9fa 0%, #ffffff 100%);
  position: relative;
}

.services-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent 0%, #c9a15e 50%, transparent 100%);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 5rem;
}

.section-badge {
  display: inline-block;
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  color: #fff;
  padding: 0.5rem 1.5rem;
  border-radius: 50px;
  font-size: 0.9rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 1.5rem;
}

.section-header h2 {
  font-size: 3rem;
  font-weight: 800;
  color: #0b1e36;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.section-subtitle {
  font-size: 1.2rem;
  color: #666;
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

.service-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 3rem;
  margin-top: 4rem;
}

.service-card {
  background: #fff;
  border-radius: 20px;
  padding: 3rem 2.5rem;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
  border: 1px solid rgba(201, 161, 94, 0.1);
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 25px 60px rgba(0, 0, 0, 0.15);
}

.service-card:hover .service-hover-effect {
  opacity: 1;
  transform: scale(1);
}

.service-hover-effect {
  position: absolute;
  top: -50%;
  right: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(135deg, rgba(201, 161, 94, 0.05) 0%, rgba(201, 161, 94, 0.1) 100%);
  border-radius: 50%;
  opacity: 0;
  transform: scale(0);
  transition: all 0.6s ease;
  z-index: 1;
}

.service-icon {
  margin-bottom: 2rem;
  position: relative;
  z-index: 2;
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
  box-shadow: 0 8px 25px rgba(201, 161, 94, 0.3);
}

.icon-wrapper svg {
  width: 40px;
  height: 40px;
}

.service-content {
  position: relative;
  z-index: 2;
}

.service-content h3 {
  font-size: 1.8rem;
  font-weight: 700;
  color: #0b1e36;
  margin-bottom: 1rem;
}

.service-content p {
  font-size: 1.1rem;
  color: #666;
  line-height: 1.7;
  margin-bottom: 2rem;
}

.service-features {
  list-style: none;
  padding: 0;
  margin: 0;
}

.service-features li {
  padding: 0.5rem 0;
  color: #555;
  position: relative;
  padding-left: 1.5rem;
}

.service-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #c9a15e;
  font-weight: bold;
}

@media (max-width: 768px) {
  .services-section {
    padding: 4rem 1rem;
  }
  
  .section-header h2 {
    font-size: 2.2rem;
  }
  
  .service-cards {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .service-card {
    padding: 2rem 1.5rem;
  }
}
</style>