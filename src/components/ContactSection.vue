<template>
  <section id="contact" class="contact-section">
    <div class="container">
      <div class="section-header">
        <span class="section-badge">Get In Touch</span>
        <h2>Ready to Find Your Perfect Property?</h2>
        <p class="section-subtitle">
          Contact our expert team today for personalized real estate solutions in Abuja
        </p>
      </div>

      <div class="contact-grid">
        <div class="contact-info">
          <div class="contact-card">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
              </svg>
            </div>
            <div class="contact-details">
              <h4>Call Us</h4>
              <p>+234 816 720 4953</p>
              <span class="availability">Available 24/7</span>
            </div>
          </div>

          <div class="contact-card">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                <polyline points="22,6 12,13 2,6"/>
              </svg>
            </div>
            <div class="contact-details">
              <h4>Email Us</h4>
              <p>info@olohimose.com</p>
              <span class="availability">Quick Response</span>
            </div>
          </div>

          <div class="contact-card">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                <circle cx="12" cy="10" r="3"/>
              </svg>
            </div>
            <div class="contact-details">
              <h4>Visit Us</h4>
              <p>39 Yaoundé Street, Wuse Zone 6, Abuja</p>
              <span class="availability">Mon - Sat, 9AM - 6PM</span>
            </div>
          </div>

          <!-- Form Submissions Counter -->
          <div class="submissions-counter">
            <div class="counter-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M16 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/>
                <circle cx="8.5" cy="7" r="4"/>
                <path d="M20 8v6"/>
                <path d="M23 11h-6"/>
              </svg>
            </div>
            <div class="counter-details">
              <h4>Form Submissions</h4>
              <p class="counter-number">{{ submissionCount }}</p>
              <span class="counter-label">Total inquiries received</span>
            </div>
          </div>
        </div>

        <div class="contact-form-container">
          <!-- Success Message -->
          <div v-if="showSuccessMessage" class="success-message">
            <div class="success-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/>
                <polyline points="22,4 12,14.01 9,11.01"/>
              </svg>
            </div>
            <h3>Message Sent Successfully!</h3>
            <p>Thank you for your inquiry. We'll get back to you within 24 hours.</p>
            <button @click="showSuccessMessage = false" class="close-success">Send Another Message</button>
          </div>

          <!-- Error Message -->
          <div v-if="showErrorMessage" class="error-message">
            <div class="error-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/>
                <line x1="15" y1="9" x2="9" y2="15"/>
                <line x1="9" y1="9" x2="15" y2="15"/>
              </svg>
            </div>
            <h3>Message Failed to Send</h3>
            <p>{{ errorMessage }}</p>
            <button @click="showErrorMessage = false" class="close-error">Try Again</button>
          </div>

          <!-- Contact Form -->
          <form v-if="!showSuccessMessage && !showErrorMessage" class="contact-form" @submit.prevent="submitForm">
            <div class="form-group">
              <label for="name">Full Name *</label>
              <input 
                type="text" 
                id="name" 
                v-model="form.name" 
                required 
                placeholder="Enter your full name"
              >
            </div>
            
            <div class="form-group">
              <label for="email">Email Address *</label>
              <input 
                type="email" 
                id="email" 
                v-model="form.email" 
                required 
                placeholder="Enter your email"
              >
            </div>
            
            <div class="form-group">
              <label for="phone">Phone Number</label>
              <input 
                type="tel" 
                id="phone" 
                v-model="form.phone" 
                placeholder="Enter your phone number"
              >
            </div>
            
            <div class="form-group">
              <label for="service">Service Interest *</label>
              <select id="service" v-model="form.service" required>
                <option value="">Select a service</option>
                <option value="property-management">Property Management</option>
                <option value="investment-consulting">Investment Consulting</option>
                <option value="property-marketing">Property Marketing</option>
                <option value="property-buying">Property Buying</option>
                <option value="property-selling">Property Selling</option>
                <option value="other">Other</option>
              </select>
            </div>
            
            <div class="form-group">
              <label for="message">Message *</label>
              <textarea 
                id="message" 
                v-model="form.message" 
                rows="4" 
                placeholder="Tell us about your property needs..."
                required
              ></textarea>
            </div>
            
            <button type="submit" class="submit-btn" :disabled="isSubmitting">
              <span v-if="!isSubmitting">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <line x1="22" y1="2" x2="11" y2="13"/>
                  <polygon points="22,2 15,22 11,13 2,9 22,2"/>
                </svg>
                Send Message
              </span>
              <span v-else>
                <div class="loading-spinner"></div>
                Sending...
              </span>
            </button>
          </form>
        </div>
      </div>

      <div class="social-section">
        <h3>Connect With Us</h3>
        <div class="social-icons">
          <a href="https://wa.me/2348167204953" target="_blank" class="social-link whatsapp">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893A11.821 11.821 0 0020.893 3.488"/>
            </svg>
          </a>
          <a href="https://instagram.com/your-profile" target="_blank" class="social-link instagram">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
            </svg>
          </a>
          <a href="https://facebook.com/your-page" target="_blank" class="social-link facebook">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
            </svg>
          </a>
          <a href="https://youtube.com/your-channel" target="_blank" class="social-link youtube">
            <svg viewBox="0 0 24 24" fill="currentColor">
              <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from '@emailjs/browser';

export default {
  name: "ContactSection",
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        service: '',
        message: ''
      },
      isSubmitting: false,
      showSuccessMessage: false,
      showErrorMessage: false,
      errorMessage: '',
      submissionCount: 0
    };
  },
  mounted() {
    // Initialize EmailJS with your public key
    emailjs.init("YOUR_PUBLIC_KEY"); // Replace with your actual public key
    
    // Load submission count from localStorage
    this.loadSubmissionCount();
  },
  methods: {
    async submitForm() {
      this.isSubmitting = true;
      
      try {
        // Prepare template parameters
        const templateParams = {
          from_name: this.form.name,
          from_email: this.form.email,
          phone: this.form.phone || 'Not provided',
          service: this.form.service,
          message: this.form.message,
          to_email: 'info@olohimose.com', // Your client's email
          submission_date: new Date().toLocaleString(),
          submission_number: this.submissionCount + 1
        };

        // Send email using EmailJS
        await emailjs.send(
          'YOUR_SERVICE_ID',    // Replace with your service ID
          'YOUR_TEMPLATE_ID',   // Replace with your template ID
          templateParams
        );

        // Success - increment counter and show success message
        this.incrementSubmissionCount();
        this.showSuccessMessage = true;
        this.resetForm();
        
      } catch (error) {
        console.error('EmailJS Error:', error);
        this.errorMessage = 'There was an error sending your message. Please try again or contact us directly.';
        this.showErrorMessage = true;
      } finally {
        this.isSubmitting = false;
      }
    },
    
    resetForm() {
      this.form = {
        name: '',
        email: '',
        phone: '',
        service: '',
        message: ''
      };
    },

    loadSubmissionCount() {
      const count = localStorage.getItem('olohimose_submission_count');
      this.submissionCount = count ? parseInt(count) : 0;
    },

    incrementSubmissionCount() {
      this.submissionCount++;
      localStorage.setItem('olohimose_submission_count', this.submissionCount.toString());
    }
  }
};
</script>

<style scoped>
.contact-section {
  padding: 8rem 2rem;
  background: linear-gradient(135deg, #f8f9fa 0%, #ffffff 100%);
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

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  margin-bottom: 5rem;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-card, .submissions-counter {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  padding: 2rem;
  background: #fff;
  border-radius: 16px;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  border: 1px solid rgba(201, 161, 94, 0.1);
}

.contact-card:hover, .submissions-counter:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.12);
}

.contact-icon, .counter-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  flex-shrink: 0;
}

.contact-icon svg, .counter-icon svg {
  width: 24px;
  height: 24px;
}

.contact-details h4, .counter-details h4 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #0b1e36;
  margin-bottom: 0.5rem;
}

.contact-details p, .counter-details p {
  font-size: 1.1rem;
  color: #333;
  margin-bottom: 0.5rem;
}

.availability, .counter-label {
  font-size: 0.9rem;
  color: #c9a15e;
  font-weight: 600;
}

.counter-number {
  font-size: 2rem !important;
  font-weight: 800 !important;
  color: #c9a15e !important;
  margin: 0.5rem 0 !important;
}

.contact-form-container {
  background: #fff;
  padding: 3rem;
  border-radius: 20px;
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.1);
  border: 1px solid rgba(201, 161, 94, 0.1);
}

.success-message, .error-message {
  text-align: center;
  padding: 3rem 2rem;
}

.success-message {
  color: #22c55e;
}

.error-message {
  color: #ef4444;
}

.success-icon, .error-icon {
  width: 80px;
  height: 80px;
  margin: 0 auto 2rem;
  background: currentColor;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
}

.success-icon {
  background: #22c55e;
}

.error-icon {
  background: #ef4444;
}

.success-icon svg, .error-icon svg {
  width: 40px;
  height: 40px;
}

.success-message h3, .error-message h3 {
  font-size: 1.8rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: #0b1e36;
}

.success-message p, .error-message p {
  font-size: 1.1rem;
  color: #666;
  margin-bottom: 2rem;
}

.close-success, .close-error {
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  color: #fff;
  padding: 1rem 2rem;
  border: none;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.close-success:hover, .close-error:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(201, 161, 94, 0.4);
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-group label {
  font-weight: 600;
  color: #0b1e36;
  margin-bottom: 0.5rem;
  font-size: 0.95rem;
}

.form-group input,
.form-group select,
.form-group textarea {
  padding: 1rem;
  border: 2px solid #e1e5e9;
  border-radius: 12px;
  font-size: 1rem;
  transition: all 0.3s ease;
  background: #fff;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #c9a15e;
  box-shadow: 0 0 0 3px rgba(201, 161, 94, 0.1);
}

.form-group textarea {
  resize: vertical;
  min-height: 120px;
}

.submit-btn {
  background: linear-gradient(135deg, #c9a15e 0%, #b8935a 100%);
  color: #fff;
  padding: 1.2rem 2rem;
  border: none;
  border-radius: 12px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(201, 161, 94, 0.4);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.submit-btn svg {
  width: 20px;
  height: 20px;
}

.loading-spinner {
  width: 20px;
  height: 20px;
  border: 2px solid rgba(255, 255, 255, 0.3);
  border-top: 2px solid #fff;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.social-section {
  text-align: center;
  padding-top: 3rem;
  border-top: 1px solid #e1e5e9;
}

.social-section h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #0b1e36;
  margin-bottom: 2rem;
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
}

.social-link {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  text-decoration: none;
}

.social-link svg {
  width: 24px;
  height: 24px;
}

.social-link.whatsapp {
  background: linear-gradient(135deg, #25D366 0%, #128C7E 100%);
  color: #fff;
}

.social-link.instagram {
  background: linear-gradient(135deg, #E4405F 0%, #C13584 50%, #833AB4 100%);
  color: #fff;
}

.social-link.facebook {
  background: linear-gradient(135deg, #1877F2 0%, #42A5F5 100%);
  color: #fff;
}

.social-link.youtube {
  background: linear-gradient(135deg, #FF0000 0%, #CC0000 100%);
  color: #fff;
}

.social-link:hover {
  transform: translateY(-3px) scale(1.05);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

@media (max-width: 768px) {
  .contact-section {
    padding: 4rem 1rem;
  }
  
  .section-header h2 {
    font-size: 2.2rem;
  }
  
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .contact-form-container {
    padding: 2rem;
  }
  
  .social-icons {
    gap: 1rem;
  }
  
  .social-link {
    width: 50px;
    height: 50px;
  }

  .success-message, .error-message {
    padding: 2rem 1rem;
  }
}
</style>