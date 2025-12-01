<template>
  <section id="services" class="services-section">
    <div class="bg-decor bg-1"></div>
    <div class="bg-decor bg-2"></div>

    <div class="container">
      <div class="header">
        <div class="pill">
          <span>Our Services</span>
        </div>
        <h2 class="title">Transportation Solutions for Every Occasion</h2>
        <p class="subtitle">
          From intimate gatherings to large corporate events, we provide premium transportation
          with unmatched comfort and reliability.
        </p>
      </div>

      <div class="services-grid">
        <div
          v-for="(service, index) in services"
          :key="index"
          class="service-card"
        >
          <div class="image-wrapper">
            <img :src="service.image" :alt="service.title" class="service-image" />
            <div class="image-overlay"></div>

            <div class="service-icon">
              <span>{{ service.icon }}</span>
            </div>
          </div>

          <div class="content">
            <h3 class="service-title">{{ service.title }}</h3>
            <p class="service-desc">{{ service.description }}</p>

            <ul class="features">
              <li v-for="(f, i) in service.features" :key="i" class="feature-item">
                <div class="dot"></div>
                {{ f }}
              </li>
            </ul>

            <button class="learn-btn">Learn More</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    icon: "🧭",
    title: "Excursion Transport",
    description:
      "Comfortable group travel for sightseeing tours, wine country trips, and scenic routes with experienced guides.",
    image:
      "https://images.unsplash.com/photo-1731014302436-89bce54c8c0c?q=80&w=1080",
    features: ["Sightseeing Tours", "Multi-Day Trips", "Custom Routes", "Professional Guides"],
  },
  {
    icon: "🚌",
    title: "Charter Buses",
    description:
      "Spacious charter buses for large groups, corporate events, conferences, and long-distance travel.",
    image:
      "https://images.unsplash.com/photo-1650439800140-216ba95eaa8d?q=80&w=1080",
    features: ["20-56 Passengers", "Climate Control", "WiFi & Entertainment", "Luggage Storage"],
  },
  {
    icon: "💼",
    title: "Corporate Services",
    description:
      "Professional transportation solutions for business events, airport transfers, and executive travel.",
    image:
      "https://images.unsplash.com/photo-1660320593205-2994d5dcdc67?q=80&w=1080",
    features: ["Airport Shuttles", "Conference Transport", "Team Building Events", "Flexible Scheduling"],
  },
  {
    icon: "❤️",
    title: "Wedding Transport",
    description:
      "Elegant transportation for wedding parties and guests. Make your special day perfect and stress-free.",
    image:
      "https://images.unsplash.com/photo-1541348263662-e068662d82af?q=80&w=1080",
    features: ["Bride & Groom Transport", "Guest Shuttles", "Decorated Vehicles", "Champagne Service"],
  },
  {
    icon: "👶",
    title: "Children Group Transport",
    description:
      "Safe and reliable transportation for school trips, camps, and youth group activities with certified safety.",
    image:
      "https://images.unsplash.com/photo-1754111411218-9128fec0b647?q=80&w=1080",
    features: ["Enhanced Safety", "Background-Checked Drivers", "Seat Belts", "Supervision Support"],
  },
  {
    icon: "👑",
    title: "VIP & Premium Cars",
    description:
      "Luxury sedans and executive vehicles for discerning clients who expect the finest service.",
    image:
      "https://images.unsplash.com/photo-1541348263662-e068662d82af?q=80&w=1080",
    features: ["Premium Sedans", "Professional Chauffeurs", "Privacy & Comfort", "Concierge Service"],
  },
]
</script>

<style scoped>
.services-section {
  position: relative;
  padding: 90px 0;
  background: white;
  overflow: hidden;
}

.bg-decor {
  position: absolute;
  width: 500px;
  height: 500px;
  background: #f5f0e8;
  opacity: 0.3;
  filter: blur(60px);
  border-radius: 999px;
}
.bg-1 {
  top: 0;
  right: -120px;
}
.bg-2 {
  bottom: 0;
  left: -120px;
}

.container {
  position: relative;
  z-index: 2;
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 16px;
}

.header {
  text-align: center;
  margin-bottom: 48px;
}

.pill {
  display: inline-block;
  padding: 10px 26px;
  border-radius: 999px;
  border: 1px solid rgba(196, 149, 74, 0.2);
  background: linear-gradient(
    to right,
    rgba(196, 149, 74, 0.1),
    rgba(212, 167, 106, 0.1)
  );
  margin-bottom: 18px;
}
.pill span {
  color: #c4954a;
}

.title {
  color: #3e342b;
  font-size: 28px;
  margin-bottom: 10px;
}

.subtitle {
  color: #6b5744;
  max-width: 700px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(330px, 1fr));
  gap: 28px;
}

.service-card {
  background: white;
  border-radius: 24px;
  overflow: hidden;
  border: 1px solid rgba(196, 149, 74, 0.2);
  transition: 0.4s ease;
  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.08);
}
.service-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 24px 60px rgba(0, 0, 0, 0.12);
}

.image-wrapper {
  position: relative;
  height: 220px;
  overflow: hidden;
}

.service-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.6s ease;
}
.service-card:hover .service-image {
  transform: scale(1.08);
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(62, 52, 43, 0.6), transparent);
}

.service-icon {
  position: absolute;
  top: 16px;
  left: 16px;
  width: 54px;
  height: 54px;
  background: white;
  border-radius: 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 26px;
  color: #c4954a;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.18);
}

.content {
  padding: 22px;
}

.service-title {
  font-size: 20px;
  color: #3e342b;
  margin-bottom: 8px;
}

.service-desc {
  font-size: 14px;
  color: #6b5744;
  margin-bottom: 14px;
}

.features {
  list-style: none;
  padding: 0;
  margin: 0 0 18px 0;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 8px;
  font-size: 14px;
  color: #6b5744;
}

.dot {
  width: 6px;
  height: 6px;
  background: #c4954a;
  border-radius: 999px;
  margin-top: 6px;
}

.learn-btn {
  width: 100%;
  padding: 10px 0;
  border-radius: 999px;
  border: none;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: white;
  font-weight: 600;
  cursor: pointer;
  transition: 0.3s ease;
}
.learn-btn:hover {
  box-shadow: 0 14px 40px rgba(196, 149, 74, 0.4);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
  }
}
</style>