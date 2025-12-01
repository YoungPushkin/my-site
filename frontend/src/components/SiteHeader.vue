<template>
  <header :class="['header', { 'header--scrolled': isScrolled }]">
    <div class="header-container">
      <div class="header-row">
        <div class="logo">
          <div :class="['logo-icon', { 'logo-icon--small': isScrolled }]">
            🚌
          </div>
          <div>
            <div :class="['logo-title', { 'logo-title--small': isScrolled }]">
              Elite Transport
            </div>
            <div class="logo-subtitle">Premium Travel Solutions</div>
          </div>
        </div>

        <nav class="nav-desktop">
          <a
            v-for="item in navItems"
            :key="item.name"
            :href="item.href"
            class="nav-link"
          >
            {{ item.name }}
            <span class="nav-underline"></span>
          </a>
        </nav>

        <div class="cta-desktop">
          <a href="tel:+15551234567" class="phone-link">
            <span class="phone-icon">📞</span>
            <span>(555) 123-4567</span>
          </a>
          <button class="quote-btn">Request Quote</button>
        </div>

        <button class="burger" @click="isMenuOpen = !isMenuOpen">
          <span v-if="!isMenuOpen">☰</span>
          <span v-else>✕</span>
        </button>
      </div>

      <div v-if="isMenuOpen" class="mobile-menu">
        <nav class="mobile-nav">
          <a
            v-for="item in navItems"
            :key="item.name"
            :href="item.href"
            class="mobile-link"
            @click="isMenuOpen = false"
          >
            {{ item.name }}
          </a>

          <a href="tel:+15551234567" class="mobile-phone">
            <span class="phone-icon">📞</span>
            <span>(555) 123-4567</span>
          </a>

          <button class="mobile-quote">Request Quote</button>
        </nav>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isMenuOpen = ref(false)
const isScrolled = ref(false)

const navItems = [
  { name: 'About', href: '#about' },
  { name: 'Services', href: '#services' },
  { name: 'Fleet', href: '#fleet' },
  { name: 'Advantages', href: '#advantages' },
  { name: 'Reviews', href: '#reviews' },
  { name: 'Contact', href: '#contact' }
]

function onScroll() {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  onScroll()
  window.addEventListener('scroll', onScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<style scoped>.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 50;
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  transition: background 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
}
.header--scrolled {
  background: rgba(255, 255, 255, 0.98);
  border-color: rgba(196, 149, 74, 0.1);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
}

.header-container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 16px;
}

.header-row {
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-icon {
  width: 48px;
  height: 48px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 26px;
  transition: transform 0.3s ease;
}
.logo-icon--small {
  transform: scale(0.92);
}

.logo-title {
  font-size: 20px;
  color: #3e342b;
  transition: font-size 0.3s ease;
}
.logo-title--small {
  font-size: 18px;
}

.logo-subtitle {
  font-size: 12px;
  color: #6b5744;
}

.nav-desktop {
  display: none;
  align-items: center;
  gap: 24px;
}

.nav-link {
  position: relative;
  padding: 4px 0;
  text-decoration: none;
  color: #6b5744;
  font-size: 14px;
  transition: color 0.3s ease;
}
.nav-link:hover {
  color: #c4954a;
}
.nav-underline {
  position: absolute;
  left: 0;
  bottom: -2px;
  width: 0;
  height: 2px;
  background: #c4954a;
  transition: width 0.3s ease;
}
.nav-link:hover .nav-underline {
  width: 100%;
}

.cta-desktop {
  display: none;
  align-items: center;
  gap: 16px;
}

.phone-link {
  display: flex;
  align-items: center;
  gap: 6px;
  text-decoration: none;
  color: #6b5744;
  font-size: 14px;
  transition: color 0.3s ease;
}
.phone-link:hover {
  color: #c4954a;
}

.phone-icon {
  font-size: 14px;
}

.quote-btn {
  padding: 10px 20px;
  border-radius: 999px;
  border: none;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: #ffffff;
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.quote-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.25);
}

.burger {
  width: 44px;
  height: 44px;
  border-radius: 12px;
  border: none;
  background: #f5f0e8;
  cursor: pointer;
  font-size: 22px;
  color: #c4954a;
  display: flex;
  align-items: center;
  justify-content: center;
}

.mobile-menu {
  padding: 16px 0 20px;
  border-top: 1px solid rgba(196, 149, 74, 0.15);
}

.mobile-nav {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.mobile-link {
  padding: 6px 0;
  text-decoration: none;
  color: #6b5744;
  font-size: 14px;
  transition: color 0.3s ease;
}
.mobile-link:hover {
  color: #c4954a;
}

.mobile-phone {
  display: flex;
  align-items: center;
  gap: 6px;
  color: #6b5744;
  font-size: 14px;
  padding: 6px 0;
}

.mobile-quote {
  margin-top: 6px;
  padding: 10px 20px;
  border-radius: 999px;
  border: none;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: #ffffff;
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
}

@media (min-width: 1024px) {
  .nav-desktop {
    display: flex;
  }
  .cta-desktop {
    display: flex;
  }
  .burger {
    display: none;
  }
  .mobile-menu {
    display: none;
  }
}</style>