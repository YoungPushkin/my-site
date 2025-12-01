<template>
  <section id="contact" class="contact-section">
    <div class="decor decor-1"></div>
    <div class="decor decor-2"></div>

    <div class="contact-container">
      <div class="contact-header">
        <div class="contact-pill">
          <span>Contact &amp; Booking</span>
        </div>
        <h2 class="contact-title">Book Your Journey Today</h2>
        <p class="contact-subtitle">
          Multiple ways to get in touch. Choose what's most convenient for you.
        </p>
      </div>

      <div class="contact-grid">
        <div class="contact-left">
          <div class="contact-card messengers">
            <h3 class="card-title">
              <span class="icon-circle">💬</span>
              <span>Quick Contact</span>
            </h3>

            <div class="messenger-list">
              <a
                href="https://t.me/yourbusiness"
                target="_blank"
                rel="noopener noreferrer"
                class="messenger-item telegram"
              >
                <div class="messenger-icon">
                  💬
                </div>
                <div>
                  <div class="messenger-title">Chat on Telegram</div>
                  <div class="messenger-sub">Instant response</div>
                </div>
              </a>

              <a
                href="https://wa.me/15551234567"
                target="_blank"
                rel="noopener noreferrer"
                class="messenger-item whatsapp"
              >
                <div class="messenger-icon">
                  💬
                </div>
                <div>
                  <div class="messenger-title">Message on WhatsApp</div>
                  <div class="messenger-sub">Fast &amp; convenient</div>
                </div>
              </a>
            </div>
          </div>

          <div class="contact-info-list">
            <a
              v-for="(info, i) in contactInfo"
              :key="i"
              :href="info.link"
              class="contact-info-item"
            >
              <div class="info-icon">
                {{ info.icon }}
              </div>
              <div>
                <div class="info-title">{{ info.title }}</div>
                <div class="info-detail">{{ info.detail }}</div>
                <div class="info-sub">{{ info.subtext }}</div>
              </div>
            </a>
          </div>

          <div class="hours-card">
            <div class="hours-header">
              <span class="icon-circle small">⏰</span>
              <h4>Operating Hours</h4>
            </div>
            <div class="hours-row">
              <span>Mon - Fri:</span>
              <span>6:00 AM - 10:00 PM</span>
            </div>
            <div class="hours-row">
              <span>Saturday:</span>
              <span>7:00 AM - 9:00 PM</span>
            </div>
            <div class="hours-row">
              <span>Sunday:</span>
              <span>8:00 AM - 8:00 PM</span>
            </div>
            <div class="hours-note">
              Emergency bookings available 24/7
            </div>
          </div>
        </div>

        <div class="contact-right">
          <div class="form-header">
            <span class="icon-circle">📅</span>
            <h3>Request a Quote</h3>
          </div>

          <form class="contact-form">
            <div class="form-row">
              <div class="form-field">
                <label>Full Name *</label>
                <input type="text" placeholder="John Smith" />
              </div>
              <div class="form-field">
                <label>Email Address *</label>
                <input type="email" placeholder="john@email.com" />
              </div>
            </div>

            <div class="form-row">
              <div class="form-field">
                <label>Phone Number *</label>
                <input type="tel" placeholder="+1 (555) 000-0000" />
              </div>
              <div class="form-field">
                <label>Travel Date</label>
                <input type="date" />
              </div>
            </div>

            <div class="form-row">
              <div class="form-field">
                <label>Service Type *</label>
                <select>
                  <option>Select a service</option>
                  <option>Excursion Transport</option>
                  <option>Charter Bus</option>
                  <option>Corporate Services</option>
                  <option>Wedding Transport</option>
                  <option>Children Group Transport</option>
                  <option>VIP &amp; Premium Cars</option>
                </select>
              </div>
              <div class="form-field">
                <label>Number of Passengers</label>
                <input type="number" min="1" placeholder="0" />
              </div>
            </div>

            <div class="form-field">
              <label>Additional Details</label>
              <textarea
                rows="5"
                placeholder="Tell us about your transportation needs, pickup location, destination, special requirements..."
              ></textarea>
            </div>

            <button type="submit" class="submit-btn">
              <span>Send Request</span>
              <span class="arrow">➜</span>
            </button>

            <p class="form-note">
              We'll get back to you within 24 hours with a personalized quote
            </p>
          </form>
        </div>
      </div>

      <div class="map-card">
        <div class="map-inner">
          <div class="map-content">
            <div class="map-icon">📍</div>
            <h4>456 Transit Boulevard</h4>
            <p>San Francisco, CA 94102</p>
            <button class="map-btn">Get Directions</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const contactInfo = [
  {
    icon: '📞',
    title: 'Call Us',
    detail: '+1 (555) 123-4567',
    subtext: 'Available 24/7',
    link: 'tel:+15551234567',
  },
  {
    icon: '✉️',
    title: 'Email Us',
    detail: 'bookings@premiumtransport.com',
    subtext: 'Quick response time',
    link: 'mailto:bookings@premiumtransport.com',
  },
  {
    icon: '📍',
    title: 'Visit Us',
    detail: '456 Transit Boulevard',
    subtext: 'San Francisco, CA 94102',
    link: '#',
  },
]
</script>

<style scoped>
.contact-section {
  position: relative;
  padding: 90px 0;
  background: linear-gradient(to bottom right, #f5f0e8, #ffffff);
  overflow: hidden;
}

.decor {
  position: absolute;
  border-radius: 999px;
  filter: blur(80px);
  opacity: 0.4;
}
.decor-1 {
  width: 360px;
  height: 360px;
  background: #c4954a1a;
  top: 80px;
  right: 60px;
}
.decor-2 {
  width: 320px;
  height: 320px;
  background: #d4a76a1a;
  bottom: 80px;
  left: 60px;
}

.contact-container {
  position: relative;
  z-index: 2;
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 16px;
}

.contact-header {
  text-align: center;
  margin-bottom: 50px;
}

.contact-pill {
  display: inline-block;
  padding: 10px 26px;
  border-radius: 999px;
  background: #ffffff;
  border: 1px solid rgba(196, 149, 74, 0.2);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
  margin-bottom: 16px;
}
.contact-pill span {
  color: #c4954a;
}

.contact-title {
  font-size: 28px;
  color: #3e342b;
  margin-bottom: 10px;
}

.contact-subtitle {
  max-width: 560px;
  margin: 0 auto;
  color: #6b5744;
  font-size: 17px;
}

.contact-grid {
  display: grid;
  grid-template-columns: minmax(0, 2fr) minmax(0, 3fr);
  gap: 36px;
  align-items: flex-start;
  margin-bottom: 36px;
}

.contact-left {
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.contact-card {
  background: #ffffff;
  border-radius: 24px;
  padding: 24px;
  border: 1px solid rgba(196, 149, 74, 0.2);
  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.08);
}

.card-title {
  display: flex;
  align-items: center;
  gap: 10px;
  color: #3e342b;
  margin-bottom: 18px;
  font-size: 18px;
}

.icon-circle {
  width: 32px;
  height: 32px;
  border-radius: 999px;
  background: #f5f0e8;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  color: #c4954a;
}
.icon-circle.small {
  width: 26px;
  height: 26px;
  font-size: 14px;
}

.messenger-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.messenger-item {
  display: flex;
  gap: 12px;
  padding: 14px 16px;
  border-radius: 18px;
  text-decoration: none;
  transition: 0.3s ease;
  border: 1px solid transparent;
  box-shadow: 0 10px 26px rgba(0, 0, 0, 0.08);
}

.messenger-item.telegram {
  background: linear-gradient(to right, #0088cc1a, #0088cc0a);
  border-color: #0088cc33;
}
.messenger-item.telegram:hover {
  border-color: #0088cc80;
}

.messenger-item.whatsapp {
  background: linear-gradient(to right, #25d3661a, #25d3660a);
  border-color: #25d36633;
}
.messenger-item.whatsapp:hover {
  border-color: #25d36680;
}

.messenger-icon {
  width: 46px;
  height: 46px;
  border-radius: 16px;
  background: #0088cc;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #ffffff;
  font-size: 24px;
  flex-shrink: 0;
}

.messenger-item.whatsapp .messenger-icon {
  background: #25d366;
}

.messenger-title {
  color: #3e342b;
  margin-bottom: 2px;
}
.messenger-sub {
  color: #6b5744;
  font-size: 13px;
}

.contact-info-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.contact-info-item {
  display: flex;
  gap: 12px;
  padding: 14px 16px;
  border-radius: 18px;
  background: #ffffff;
  border: 1px solid rgba(196, 149, 74, 0.15);
  text-decoration: none;
  color: inherit;
  transition: 0.3s ease;
  box-shadow: 0 10px 26px rgba(0, 0, 0, 0.06);
}
.contact-info-item:hover {
  border-color: rgba(196, 149, 74, 0.4);
  box-shadow: 0 18px 36px rgba(0, 0, 0, 0.08);
}

.info-icon {
  width: 42px;
  height: 42px;
  border-radius: 14px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  display: flex;
  align-items: center;
  justify-content: center;
  color: #ffffff;
  flex-shrink: 0;
}

.info-title {
  color: #6b5744;
  font-size: 13px;
  margin-bottom: 2px;
}
.info-detail {
  color: #3e342b;
  font-size: 14px;
}
.info-sub {
  color: #6b5744;
  font-size: 13px;
}

.hours-card {
  background: #ffffff;
  border-radius: 18px;
  padding: 18px 20px;
  border: 1px solid rgba(196, 149, 74, 0.15);
  box-shadow: 0 12px 28px rgba(0, 0, 0, 0.06);
}

.hours-header {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 10px;
  color: #3e342b;
}
.hours-header h4 {
  font-size: 16px;
}

.hours-row {
  display: flex;
  justify-content: space-between;
  color: #6b5744;
  font-size: 14px;
}

.hours-note {
  border-top: 1px solid rgba(196, 149, 74, 0.2);
  margin-top: 8px;
  padding-top: 6px;
  font-size: 13px;
  color: #c4954a;
}

.contact-right {
  background: #ffffff;
  border-radius: 28px;
  padding: 26px 24px 30px;
  border: 1px solid rgba(196, 149, 74, 0.2);
  box-shadow: 0 22px 50px rgba(0, 0, 0, 0.12);
}

.form-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 18px;
}
.form-header h3 {
  color: #3e342b;
  font-size: 20px;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 14px;
}

.form-field label {
  display: block;
  margin-bottom: 6px;
  color: #3e342b;
  font-size: 14px;
}

.form-field input,
.form-field select,
.form-field textarea {
  width:75%;
  border-radius: 14px;
  border: 1px solid rgba(196, 149, 74, 0.3);
  background: #f5f0e880;
  padding: 10px 12px;
  font-size: 20px;
  color: #3e342b;
  outline: none;
  transition: 0.2s ease;
  resize: none;
}

.form-field input:focus,
.form-field select:focus,
.form-field textarea:focus {
  border-color: #c4954a;
  box-shadow: 0 0 0 2px rgba(196, 149, 74, 0.25);
  background: #fdf8f0;
}

.submit-btn {
  margin-top: 4px;
  width: 100%;
  padding: 12px 0;
  border-radius: 999px;
  border: none;
  cursor: pointer;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: #ffffff;
  font-weight: 600;
  font-size: 15px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.2);
  transition: 0.25s ease;
}
.submit-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.28);
}
.submit-btn .arrow {
  display: inline-block;
  transform: translateX(0);
  transition: transform 0.2s ease;
}
.submit-btn:hover .arrow {
  transform: translateX(4px);
}

.form-note {
  margin-top: 6px;
  text-align: center;
  font-size: 13px;
  color: #6b5744;
}

.map-card {
  background: #ffffff;
  border-radius: 28px;
  border: 1px solid rgba(196, 149, 74, 0.15);
  box-shadow: 0 22px 50px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.map-inner {
  height: 260px;
  background: linear-gradient(to bottom right, #f5f0e8, #e5ded0);
  display: flex;
  align-items: center;
  justify-content: center;
}

.map-content {
  text-align: center;
  color: #3e342b;
}

.map-icon {
  font-size: 40px;
  margin-bottom: 6px;
}

.map-content h4 {
  margin-bottom: 4px;
}

.map-content p {
  color: #6b5744;
  font-size: 14px;
}

.map-btn {
  margin-top: 14px;
  padding: 10px 22px;
  border-radius: 999px;
  border: none;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: #ffffff;
  font-size: 14px;
  cursor: pointer;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
  transition: 0.2s ease;
}
.map-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.26);
}

@media (max-width: 900px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 600px) {
  .form-row {
    grid-template-columns: 1fr;
  }
}
</style>
