<template>
  <section id="fleet" class="fleet-section">
    <div class="container">
      <div class="header">
        <div class="pill"><span>Our Fleet</span></div>
        <h2 class="title">Premium Vehicles for Every Need</h2>
        <p class="subtitle">
          Choose from our diverse selection of meticulously maintained vehicles, each designed
          to provide the ultimate in comfort, safety, and style.
        </p>
      </div>

      <div class="fleet-grid">
        <div
          v-for="(vehicle, index) in vehicles"
          :key="index"
          class="vehicle-card"
        >
          <div v-if="vehicle.badge" class="badge">{{ vehicle.badge }}</div>

          <div class="image-wrapper">
            <img :src="vehicle.image" :alt="vehicle.name" class="vehicle-image" />
            <div class="image-overlay"></div>
          </div>

          <div class="content">
            <div class="top-row">
              <h3 class="vehicle-name">{{ vehicle.name }}</h3>
              <div class="capacity">{{ vehicle.capacity }}</div>
            </div>

            <div class="features-grid">
              <div
                v-for="(f, i) in vehicle.features"
                :key="i"
                class="feature-item"
              >
                <div class="dot"></div>
                <span>{{ f }}</span>
              </div>
            </div>

            <button class="view-btn">View Details</button>
          </div>
        </div>
      </div>

      <div class="benefits">
        <h3 class="benefits-title">Why Choose Our Fleet</h3>
        <div class="benefits-grid">
          <div
            v-for="(b, i) in benefits"
            :key="i"
            class="benefit-card"
          >
            <div class="benefit-icon">{{ b.icon }}</div>
            <h4 class="benefit-title">{{ b.title }}</h4>
            <p class="benefit-desc">{{ b.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const vehicles = [
  {
    name: "Executive Coach",
    capacity: "56 Passengers",
    image:
      "https://images.unsplash.com/photo-1650439800140-216ba95eaa8d?q=80&w=1080",
    features: [
      "Reclining Leather Seats",
      "WiFi & USB Charging",
      "Restroom Onboard",
      "Premium Sound System",
    ],
    badge: "Most Popular",
  },
  {
    name: "Mini Coach",
    capacity: "24 Passengers",
    image:
      "https://images.unsplash.com/photo-1731014302436-89bce54c8c0c?q=80&w=1080",
    features: [
      "Comfortable Seating",
      "Climate Control",
      "Large Windows",
      "Entertainment System",
    ],
    badge: null,
  },
  {
    name: "Luxury Sedan",
    capacity: "3 Passengers",
    image:
      "https://images.unsplash.com/photo-1541348263662-e068662d82af?q=80&w=1080",
    features: [
      "Premium Leather Interior",
      "Privacy Partition",
      "Bottled Water",
      "Professional Chauffeur",
    ],
    badge: "VIP Choice",
  },
  {
    name: "Executive Van",
    capacity: "12 Passengers",
    image:
      "https://images.unsplash.com/photo-1660320593205-2994d5dcdc67?q=80&w=1080",
    features: [
      "Captain Chairs",
      "Ample Luggage Space",
      "WiFi Available",
      "Premium Comfort",
    ],
    badge: null,
  },
]

const benefits = [
  { icon: "✔️", title: "Meticulously Maintained", description: "Regular inspections and servicing" },
  { icon: "⭐", title: "Latest Models", description: "Modern, fuel-efficient vehicles" },
  { icon: "👥", title: "Trained Drivers", description: "Experienced and professional" },
  { icon: "📶", title: "Modern Amenities", description: "WiFi, charging, and more" },
]
</script>

<style>
.fleet-section {
  padding: 0px 0;
  background: linear-gradient(to bottom, #ffffff, #f5f0e84d, #ffffff);
}

.container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 0px;
}

.header {
  text-align: center;
  margin-bottom: 50px;
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
  margin-bottom: 16px;
}
.pill span {
  color: #c4954a;
}

.title {
  font-size: 28px;
  color: #3e342b;
  margin-bottom: 12px;
}

.subtitle {
  color: #6b5744;
  max-width: 700px;
  margin: 0 auto;
}

.fleet-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(460px, 1fr));
  gap: 30px;
  margin-bottom: 60px;
}

.vehicle-card {
  background: white;
  border-radius: 28px;
  overflow: hidden;
  border: 1px solid rgba(196, 149, 74, 0.15);
  transition: 0.4s ease;
  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.1);
}
.vehicle-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 24px 60px rgba(0, 0, 0, 0.14);
}

.badge {
  position: absolute;
  top: 20px;
  right: 20px;
  padding: 10px 20px;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: white;
  border-radius: 999px;
  font-size: 14px;
  font-weight: 600;
  z-index: 20;
  box-shadow: 0 6px 20px rgba(0,0,0,0.2);
}
.image-wrapper {
  position: relative;
  z-index: 10;
}
.vehicle-card {
  position: relative;
}
.vehicle-image {
  width: 100%;
  height: 260px;
  object-fit: cover;
  transition: transform 0.6s ease;
}
.vehicle-card:hover .vehicle-image {
  transform: scale(1.08);
}
.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, #3e342b80, transparent);
}

.content {
  padding: 26px;
}

.top-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 14px;
}

.vehicle-name {
  color: #3e342b;
  font-size: 20px;
}

.capacity {
  background: #f5f0e8;
  padding: 6px 14px;
  border-radius: 999px;
  font-size: 13px;
  color: #c4954a;
}

.features-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.feature-item {
  display: flex;
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

.view-btn {
  width: 100%;
  margin-top: 18px;
  padding: 12px 0;
  border-radius: 999px;
  border: 1px solid rgba(196, 149, 74, 0.25);
  background: linear-gradient(to right, #c4954a1a, #d4a76a1a);
  color: #c4954a;
  transition: 0.3s ease;
}
.view-btn:hover {
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: white;
}

.benefits {
  background: white;
  border-radius: 28px;
  padding: 40px 26px 50px;
  border: 1px solid rgba(196, 149, 74, 0.15);
  box-shadow: 0 24px 60px rgba(0, 0, 0, 0.08);
}

.benefits-title {
  text-align: center;
  font-size: 24px;
  color: #3e342b;
  margin-bottom: 28px;
}

.benefits-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 30px;
}

.benefit-card {
  text-align: center;
}

.benefit-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: white;
  border-radius: 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto 14px;
  font-size: 26px;
}

.benefit-title {
  color: #3e342b;
  margin-bottom: 4px;
}

.benefit-desc {
  color: #6b5744;
  font-size: 14px;
}
</style>