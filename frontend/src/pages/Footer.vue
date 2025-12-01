<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-top">
        <div class="footer-brand">
          <div class="brand-row">
            <div class="brand-logo">🚌</div>
            <div>
              <div class="brand-name">Elite Transport</div>
              <div class="brand-sub">Premium Travel Solutions</div>
            </div>
          </div>
          <p class="brand-text">
            Your trusted partner for premium charter buses, luxury excursions, and sophisticated
            transportation services. Travel in comfort, arrive in style.
          </p>

          <div class="brand-contacts">
            <a href="tel:+15551234567" class="contact-row">
              <div class="contact-icon">📞</div>
              <span>(555) 123-4567</span>
            </a>
            <a href="mailto:info@elitetransport.com" class="contact-row">
              <div class="contact-icon">✉️</div>
              <span>info@elitetransport.com</span>
            </a>
            <div class="contact-row contact-row--address">
              <div class="contact-icon">📍</div>
              <span>456 Transit Boulevard<br />San Francisco, CA 94102</span>
            </div>
          </div>
        </div>

        <div class="footer-links-grid">
          <div
            v-for="section in footerLinks"
            :key="section.title"
            class="links-section"
          >
            <h4 class="links-title">{{ section.title }}</h4>
            <ul class="links-list">
              <li
                v-for="link in section.links"
                :key="link"
              >
                <a href="#" class="link-item">
                  {{ link }}
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <div class="newsletter">
        <div class="newsletter-inner">
          <div>
            <h4 class="newsletter-title">Stay Updated</h4>
            <p class="newsletter-text">Subscribe to receive exclusive offers and travel tips</p>
          </div>
          <div class="newsletter-form">
            <input
              type="email"
              placeholder="Enter your email"
              class="newsletter-input"
            />
            <button class="newsletter-btn">Subscribe</button>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <div class="copy">
          © {{ currentYear }} Elite Transport. All rights reserved.
        </div>

        <div class="socials">
          <a
            v-for="social in socialLinks"
            :key="social.label"
            :href="social.href"
            :aria-label="social.label"
            class="social-btn"
          >
            <span>{{ social.icon }}</span>
          </a>
        </div>

        <div class="badges">
          <div class="badge">DOT Certified</div>
          <div class="badge">Fully Insured</div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear()

const footerLinks = [
  {
    title: 'Services',
    links: [
      'Charter Buses',
      'Excursion Tours',
      'Luxury Vehicles',
      'Corporate Transport',
      'Wedding Shuttles',
      'Airport Transfers',
    ],
  },
  {
    title: 'Company',
    links: ['About Us', 'Our Fleet', 'Safety Standards', 'Careers', 'Blog', 'Press'],
  },
  {
    title: 'Support',
    links: ['Contact Us', 'Get a Quote', 'Book Online', 'FAQs', 'Payment Options', 'Cancellation Policy'],
  },
  {
    title: 'Legal',
    links: ['Privacy Policy', 'Terms of Service', 'Cookie Policy', 'Accessibility', 'Insurance Info', 'Licensing'],
  },
]

const socialLinks = [
  { label: 'Facebook', href: '#', icon: '📘' },
  { label: 'Twitter', href: '#', icon: '🐦' },
  { label: 'LinkedIn', href: '#', icon: '💼' },
  { label: 'Instagram', href: '#', icon: '📸' },
]
</script>

<style scoped>
.footer {
  background: linear-gradient(to bottom, #3e342b, #2a231d);
  color: #ffffff;
}

.footer-container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 48px 16px 28px;
}

.footer-top {
  display: grid;
  grid-template-columns: minmax(0, 2.1fr) minmax(0, 3fr);
  gap: 36px;
  margin-bottom: 32px;
}

.footer-brand {
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.brand-row {
  display: flex;
  align-items: center;
  gap: 10px;
}

.brand-logo {
  width: 48px;
  height: 48px;
  border-radius: 14px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 26px;
  box-shadow: 0 14px 32px rgba(0, 0, 0, 0.4);
}

.brand-name {
  font-size: 18px;
  font-weight: 500;
}

.brand-sub {
  font-size: 11px;
  color: rgba(255, 255, 255, 0.7);
}

.brand-text {
  color: rgba(255, 255, 255, 0.7);
  font-size: 14px;
  line-height: 1.7;
}

.brand-contacts {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.contact-row {
  display: flex;
  align-items: center;
  gap: 10px;
  color: rgba(255, 255, 255, 0.7);
  text-decoration: none;
  font-size: 14px;
  transition: color 0.2s ease;
}
.contact-row:hover {
  color: #ffffff;
}
.contact-row--address {
  align-items: flex-start;
}

.contact-icon {
  width: 36px;
  height: 36px;
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.06);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.footer-links-grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 18px;
}

.links-section {
  min-width: 0;
}

.links-title {
  font-size: 15px;
  margin-bottom: 10px;
}

.links-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.link-item {
  display: inline-block;
  padding: 3px 0;
  font-size: 13px;
  color: rgba(255, 255, 255, 0.7);
  text-decoration: none;
  transition: color 0.2s ease, transform 0.2s ease;
}
.link-item:hover {
  color: #c4954a;
  transform: translateX(2px);
}

.newsletter {
  margin-bottom: 28px;
}

.newsletter-inner {
  border-radius: 18px;
  padding: 18px 18px;
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(255, 255, 255, 0.14);
  display: grid;
  grid-template-columns: minmax(0, 1.4fr) minmax(0, 2fr);
  gap: 18px;
  align-items: center;
}

.newsletter-title {
  font-size: 16px;
  margin-bottom: 3px;
}

.newsletter-text {
  font-size: 13px;
  color: rgba(255, 255, 255, 0.7);
}

.newsletter-form {
  display: flex;
  gap: 10px;
}

.newsletter-input {
  flex: 1;
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.26);
  background: rgba(255, 255, 255, 0.08);
  padding: 8px 12px;
  font-size: 13px;
  color: #ffffff;
  outline: none;
  min-width: 0;
}
.newsletter-input::placeholder {
  color: rgba(255, 255, 255, 0.55);
}
.newsletter-input:focus {
  border-color: #c4954a;
  box-shadow: 0 0 0 2px rgba(196, 149, 74, 0.4);
}

.newsletter-btn {
  padding: 8px 16px;
  border-radius: 12px;
  border: none;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: #ffffff;
  font-size: 13px;
  font-weight: 500;
  cursor: pointer;
  white-space: nowrap;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.35);
  transition: 0.2s ease;
}
.newsletter-btn:hover {
  transform: translateY(-1px);
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.45);
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.14);
  padding-top: 14px;
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  align-items: center;
  justify-content: space-between;
}

.copy {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.7);
}

.socials {
  display: flex;
  gap: 8px;
}

.social-btn {
  width: 34px;
  height: 34px;
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.08);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 17px;
  text-decoration: none;
  transition: 0.25s ease;
}
.social-btn:hover {
  background: #c4954a;
  transform: scale(1.08);
}

.badges {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.badge {
  padding: 4px 10px;
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.2);
  font-size: 12px;
  color: rgba(255, 255, 255, 0.8);
}

@media (max-width: 900px) {
  .footer-top {
    grid-template-columns: 1fr;
  }

  .footer-links-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .newsletter-inner {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 600px) {
  .footer-links-grid {
    grid-template-columns: 1fr 1fr;
  }
  .newsletter-form {
    flex-direction: column;
  }
  .newsletter-btn {
    width: 100%;
    text-align: center;
    justify-content: center;
  }
  .footer-bottom {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>
