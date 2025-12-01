<template>
  <section class="hero">
    <!-- ФОН -->
    <div class="hero-bg">
      <img :src="heroImage" alt="Premium luxury transportation" class="hero-bg-image" />
      <div class="hero-bg-overlay overlay-main"></div>
      <div class="hero-bg-overlay overlay-top"></div>
    </div>

    <!-- КОНТЕНТ -->
    <div class="hero-inner">
      <div class="hero-content">
        <!-- бейдж -->
        <div class="hero-badge">
          <div class="hero-badge-dot"></div>
          <span>Premium Transportation Services Since 1999</span>
        </div>

        <!-- заголовок -->
        <h1 class="hero-title">
          Comfort, Reliability, Premium Service
        </h1>

        <!-- подзаголовок -->
        <p class="hero-subtitle">
          Professional passenger transportation for any occasion. Modern fleet, experienced
          drivers, and unwavering commitment to your safety and comfort.
        </p>

        <!-- три “пилюли” доверия -->
        <div class="hero-trust">
          <div v-for="(item, i) in trustItems" :key="i" class="trust-pill">
            <div class="trust-icon">
              <span>{{ item.icon }}</span>
            </div>
            <span>{{ item.text }}</span>
          </div>
        </div>

        <!-- CTA кнопки -->
        <div class="hero-cta">
          <button class="btn-primary">
            Book Transport
            <span class="arrow">→</span>
          </button>
          <button class="btn-outline">
            Get a Free Quote
          </button>
        </div>

        <!-- быстрые контакты -->
        <div class="hero-contacts">
          <span class="contacts-label">Quick contact:</span>
          <div class="contacts-buttons">
            <a
              href="https://t.me/yourbusiness"
              target="_blank"
              rel="noopener noreferrer"
              class="contact-btn contact-telegram"
            >
              💬 <span>Telegram</span>
            </a>
            <a
              href="https://wa.me/15551234567"
              target="_blank"
              rel="noopener noreferrer"
              class="contact-btn contact-whatsapp"
            >
              💬 <span>WhatsApp</span>
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- индикатор скролла -->
    <div class="scroll-indicator">
      <div class="scroll-shell">
        <div class="scroll-dot"></div>
      </div>
    </div>
  </section>
</template>
<script setup>
import heroImage from '../assets/audiozs.jpg'

const trustItems = [
  { icon: '🛡️', text: 'Licensed & Insured' },
  { icon: '⏰', text: '24/7 Availability' },
  { icon: '❤️', text: '50,000+ Happy Clients' },
]
</script>
<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  color: #fff;
}

/* ФОН */
.hero-bg {
  position: absolute;
  inset: 0;
  z-index: 0;
}

.hero-bg-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-bg-overlay {
  position: absolute;
  inset: 0;
}

.overlay-main {
  background: linear-gradient(
    135deg,
    rgba(62, 52, 43, 0.92),
    rgba(107, 87, 68, 0.75),
    rgba(196, 149, 74, 0.7)
  );
}

.overlay-top {
  background: linear-gradient(
    to top,
    rgba(62, 52, 43, 0.9),
    transparent
  );
}

/* КОНТЕНТ */
.hero-inner {
  position: relative;
  z-index: 1;
  max-width: 1120px;
  margin: 0 auto;
  padding: 120px 24px 80px;
  display: flex;
  justify-content: center;
}

.hero-content {
  max-width: 780px;
  text-align: center;
}

/* бейдж */
.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 18px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.12);
  border: 1px solid rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(12px);
  margin-bottom: 24px;
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.35);
}

.hero-badge-dot {
  width: 8px;
  height: 8px;
  border-radius: 999px;
  background: #c4954a;
  animation: pulse 1.5s infinite;
}

.hero-badge span {
  font-size: 14px;
}

/* заголовок */
.hero-title {
  font-size: 36px;
  line-height: 1.2;
  margin-bottom: 18px;
  text-shadow: 0 6px 20px rgba(0, 0, 0, 0.5);
}

/* подзаголовок */
.hero-subtitle {
  font-size: 18px;
  line-height: 1.6;
  margin: 0 auto 26px;
  max-width: 680px;
  color: rgba(255, 255, 255, 0.92);
}

/* ПИЛЮЛИ ДОВЕРИЯ */
.hero-trust {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 16px;
  margin-bottom: 28px;
}

.trust-pill {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px 18px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.12);
  border: 1px solid rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(8px);
  font-size: 14px;
}

.trust-icon {
  width: 36px;
  height: 36px;
  border-radius: 999px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 10px 26px rgba(0, 0, 0, 0.5);
}

/* CTA */
.hero-cta {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 14px;
  margin-bottom: 26px;
}

.btn-primary,
.btn-outline {
  padding: 13px 28px;
  border-radius: 999px;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  border: 2px solid transparent;
  transition: transform 0.2s ease, box-shadow 0.2s ease, background 0.2s ease,
    border-color 0.2s ease;
}

.btn-primary {
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: #ffffff;
  box-shadow: 0 14px 32px rgba(0, 0, 0, 0.5);
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

.btn-primary .arrow {
  display: inline-block;
  transition: transform 0.2s ease;
}

.btn-primary:hover .arrow {
  transform: translateX(4px);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.6);
}

.btn-outline {
  background: rgba(255, 255, 255, 0.08);
  border-color: rgba(255, 255, 255, 0.4);
  color: #ffffff;
  backdrop-filter: blur(12px);
  box-shadow: 0 10px 26px rgba(0, 0, 0, 0.35);
}

.btn-outline:hover {
  background: rgba(255, 255, 255, 0.18);
  border-color: rgba(255, 255, 255, 0.7);
  transform: translateY(-2px);
}

/* КОНТАКТЫ */
.hero-contacts {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

.contacts-label {
  font-size: 14px;
  color: rgba(255, 255, 255, 0.8);
}

.contacts-buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.contact-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 20px;
  border-radius: 999px;
  border: 1px solid transparent;
  color: #ffffff;
  font-size: 14px;
  text-decoration: none;
  box-shadow: 0 10px 26px rgba(0, 0, 0, 0.45);
  backdrop-filter: blur(10px);
  transition: background 0.2s ease, border-color 0.2s ease,
    transform 0.2s ease;
}

.contact-telegram {
  background: rgba(0, 136, 204, 0.22);
  border-color: rgba(0, 136, 204, 0.5);
}

.contact-telegram:hover {
  background: rgba(0, 136, 204, 0.35);
  border-color: rgba(0, 136, 204, 0.8);
  transform: translateY(-2px);
}

.contact-whatsapp {
  background: rgba(37, 211, 102, 0.22);
  border-color: rgba(37, 211, 102, 0.5);
}

.contact-whatsapp:hover {
  background: rgba(37, 211, 102, 0.35);
  border-color: rgba(37, 211, 102, 0.8);
  transform: translateY(-2px);
}

/* ИНДИКАТОР СКРОЛЛА */
.scroll-indicator {
  position: absolute;
  bottom: 32px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1;
  animation: bounce 1.8s infinite;
}

.scroll-shell {
  width: 24px;
  height: 40px;
  border-radius: 999px;
  border: 2px solid rgba(255, 255, 255, 0.5);
  display: flex;
  padding: 4px;
  align-items: flex-start;
  justify-content: center;
}

.scroll-dot {
  width: 6px;
  height: 6px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.8);
}

/* АНИМАЦИИ */
@keyframes pulse {
  0%,
  100% {
    transform: scale(1);
    opacity: 0.9;
  }
  50% {
    transform: scale(1.4);
    opacity: 0.4;
  }
}

@keyframes bounce {
  0%,
  100% {
    transform: translate(-50%, 0);
  }
  50% {
    transform: translate(-50%, -8px);
  }
}

/* АДАПТИВ */
@media (max-width: 768px) {
  .hero-inner {
    padding: 110px 16px 72px;
  }

  .hero-title {
    font-size: 26px;
  }

  .hero-subtitle {
    font-size: 16px;
  }

  .btn-primary,
  .btn-outline {
    width: 100%;
    max-width: 260px;
  }

  .hero-cta {
    gap: 10px;
  }

  .hero-contacts {
    gap: 8px;
  }

  .contacts-buttons {
    justify-content: center;
  }
}
</style>