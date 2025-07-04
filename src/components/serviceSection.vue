<!-- src/components/ServicesSection.vue -->
<template>
  <section id="services" class="services-section">
    <div class="container">
      <h2>Our Services</h2>
      <div class="service-cards">
        <div class="service-card">
          <h3>Property Management</h3>
          <p>We manage and maintain your properties efficiently.</p>
        </div>
        <div class="service-card">
          <h3>Investment Consulting</h3>
          <p>Expert advice to maximize your real estate investments.</p>
        </div>
        <div class="service-card">
          <h3>Property Listings</h3>
          <p>Showcasing your properties to the right audience.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ServicesSection",
};
</script>

<style scoped>
.services-section {
  padding: 4rem 2rem;
  text-align: center;
  background-color: #0b1e36;
  color: #fff;
}

.services-section h2 {
  font-size: 2rem;
  margin-bottom: 1.5rem;
}

.service-cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
}

.service-card {
  flex: 1 1 250px;
  background-color: #fff;
  color: #0b1e36;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}
</style>
