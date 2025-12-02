<template>
  <section
    id="about"
    class="about-section"
  >
    <!-- декоративный фон -->
    <div class="about-bg">
      <div class="bg-circle bg-circle-1"></div>
      <div class="bg-circle bg-circle-2"></div>
    </div>

    <div class="about-inner">
      <!-- HEADER -->
      <div class="about-header">
        <div class="about-pill">
          <span>About Us</span>
        </div>
        <h2 class="about-heading">Your Trusted Transportation Partner</h2>
        <p class="about-lead">
          With over 25 years of experience, we've built our reputation on reliability,
          comfort, and exceptional service.
        </p>
      </div>

      <!-- MAIN GRID -->
      <div class="about-main">
        <!-- LEFT: IMAGE + FLOATING CARD -->
        <div class="about-image-wrapper">
          <div class="about-image-card">
            <img
              src="/src/assets/autobus.jpeg"
              alt="Modern bus fleet"
            />
            <div class="about-image-overlay"></div>
          </div>

          <div class="floating-card">
            <div class="floating-icon">
              🏅
            </div>
            <div>
              <div class="floating-title">DOT Certified</div>
              <div class="floating-sub">Premium Standards</div>
            </div>
          </div>
        </div>

        <!-- RIGHT: TEXT + FEATURE CARDS -->
        <div class="about-content">
          <h3 class="about-subheading">
            Professional Passenger Transportation for Every Occasion
          </h3>

          <p class="about-text">
            We are a leading transportation company specializing in premium passenger services.
            Our modern fleet and experienced team ensure that every journey is comfortable, safe,
            and memorable.
          </p>

          <div class="about-features">
            <div
              v-for="(item, index) in features"
              :key="index"
              class="feature-card"
            >
              <div class="feature-dot"></div>
              <div>
                <h4 class="feature-title">{{ item.title }}</h4>
                <p class="feature-desc">{{ item.description }}</p>
              </div>
            </div>
          </div>

          <button class="learn-btn">
            Learn More About Us
          </button>
        </div>
      </div>

      <!-- STATS GRID -->
      <div class="stats-grid">
        <div
          v-for="(item, index) in highlights"
          :key="index"
          class="stat-card"
        >
          <div class="stat-icon">
            <span>{{ item.icon }}</span>
          </div>
          <div class="stat-number">{{ item.number }}</div>
          <div class="stat-label">{{ item.label }}</div>
          <div class="stat-desc">{{ item.description }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
    const features = [
    {
        title: 'Modern Fleet',
        description:
        'Regularly maintained, latest models with premium amenities and comfort features.',
    },
    {
        title: 'Professional Drivers',
        description:
        'Highly trained, courteous, and experienced professionals committed to your safety.',
    },
    {
        title: 'Safety First',
        description:
        'Comprehensive insurance, GPS tracking, and strict adherence to all safety regulations.',
    },
    {
        title: 'Customer Comfort',
        description:
        'Climate control, spacious seating, entertainment systems, and premium service standards.',
    },
    ]

    const highlights = [
    {
        icon: '🏅',
        number: '25+',
        label: 'Years of Excellence',
        description: 'Trusted industry leader',
    },
    {
        icon: '👥',
        number: '50K+',
        label: 'Happy Passengers',
        description: 'Every year',
    },
    {
        icon: '🛡️',
        number: '100%',
        label: 'Safety Record',
        description: 'Fully certified fleet',
    },
    {
        icon: '📈',
        number: '98%',
        label: 'Client Retention',
        description: 'Return customers',
    },
    ]
</script>

<style scoped>

.about-section {
  position: relative;
  overflow: hidden;
  padding: 96px 0;
  background: linear-gradient(
    to bottom,
    #ffffff,
    rgba(245, 240, 232, 0.3),
    #ffffff
  );
}

.about-bg {
  position: absolute;
  inset: 0;
  pointer-events: none;
  opacity: 0.3;
}

.bg-circle {
  position: absolute;
  border-radius: 999px;
  filter: blur(60px);
}

.bg-circle-1 {
  top: 80px;
  right: -150px;
  width: 600px;
  height: 600px;
  background: rgba(196, 149, 74, 0.3);
}

.bg-circle-2 {
  bottom: -150px;
  left: -150px;
  width: 500px;
  height: 500px;
  background: rgba(212, 167, 106, 0.3);
}

/* INNER WRAPPER */
.about-inner {
  position: relative;
  z-index: 1;
  max-width: 1120px;
  margin: 0 auto;
  padding: 0 24px;
}

/* HEADER */
.about-header {
  text-align: center;
  margin-bottom: 64px;
}

.about-pill {
  display: inline-block;
  padding: 8px 20px;
  border-radius: 999px;
  border: 1px solid rgba(196, 149, 74, 0.2);
  background: linear-gradient(
    to right,
    rgba(196, 149, 74, 0.1),
    rgba(212, 167, 106, 0.1)
  );
  margin-bottom: 16px;
}

.about-pill span {
  color: #c4954a;
  font-size: 20px;
}

.about-heading {
  font-size: 28px;
  color: #3e342b;
  margin-bottom: 16px;
}

.about-lead {
  max-width: 720px;
  margin: 0 auto;
  color: #6b5744;
  font-size: 18px;
}

/* MAIN GRID */
.about-main {
  display: grid;
  grid-template-columns: minmax(0, 1.1fr) minmax(0, 1fr);
  gap: 48px;
  align-items: center;
  margin-bottom: 80px;
}

/* LEFT IMAGE BLOCK */
.about-image-wrapper {
  position: relative;
}

.about-image-card {
  position: relative;
  border-radius: 24px;
  overflow: hidden;
  box-shadow: 0 24px 60px rgba(15, 23, 42, 0.4);
}

.about-image-card img {
  display: block;
  width: 100%;
  height: 480px;
  object-fit: cover;
}

.about-image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(62, 52, 43, 0.5), transparent);
}

/* FLOATING CARD */
.floating-card {
  position: absolute;
  right: -24px;
  bottom: -24px;
  background: #ffffff;
  border-radius: 18px;
  padding: 16px 20px;
  box-shadow: 0 24px 60px rgba(0, 0, 0, 0.25);
  border: 1px solid rgba(196, 149, 74, 0.2);
  max-width: 260px;
  display: flex;
  gap: 12px;
  align-items: center;
}

.floating-icon {
  width: 48px;
  height: 48px;
  border-radius: 14px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 26px;
}

.floating-title {
  color: #3e342b;
  font-weight: 600;
}

.floating-sub {
  color: #6b5744;
  font-size: 13px;
}

/* RIGHT CONTENT */
.about-content {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.about-subheading {
  font-size: 22px;
  color: #3e342b;
}

.about-text {
  color: #6b5744;
  line-height: 1.6;
}

/* FEATURE CARDS */
.about-features {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-top: 8px;
}

.feature-card {
  display: flex;
  gap: 12px;
  padding: 14px 16px;
  background: #ffffff;
  border-radius: 18px;
  border: 1px solid rgba(196, 149, 74, 0.2);
  transition: box-shadow 0.3s ease, transform 0.3s ease;
}

.feature-card:hover {
  box-shadow: 0 18px 40px rgba(148, 163, 184, 0.35);
  transform: translateY(-2px);
}

.feature-dot {
  width: 8px;
  height: 8px;
  border-radius: 999px;
  background: #c4954a;
  margin-top: 8px;
  flex-shrink: 0;
}

.feature-title {
  color: #3e342b;
  margin-bottom: 2px;
}

.feature-desc {
  color: #6b5744;
  font-size: 13px;
}

/* BUTTON */
.learn-btn {
  margin-top: 10px;
  padding: 12px 28px;
  border-radius: 999px;
  border: none;
  cursor: pointer;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  color: #ffffff;
  font-weight: 600;
  font-size: 15px;
  box-shadow: 0 10px 30px rgba(196, 149, 74, 0.5);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.learn-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 14px 40px rgba(196, 149, 74, 0.6);
}

/* STATS GRID */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 20px;
}

.stat-card {
  text-align: center;
  padding: 32px 20px;
  background: #ffffff;
  border-radius: 24px;
  border: 1px solid rgba(196, 149, 74, 0.15);
  box-shadow: 0 14px 40px rgba(0, 0, 0, 0.12);
  transition: box-shadow 0.3s ease, transform 0.3s ease;
}

.stat-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 18px 50px rgba(0, 0, 0, 0.16);
}

.stat-icon {
  width: 60px;
  height: 60px;
  border-radius: 18px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 12px;
  font-size: 30px;
  color: #ffffff;
}

.stat-number {
  color: #c4954a;
  margin-bottom: 4px;
  font-weight: 600;
}

.stat-label {
  color: #3e342b;
  margin-bottom: 2px;
}

.stat-desc {
  color: #6b5744;
  font-size: 13px;
}

/* RESPONSIVE */
@media (max-width: 960px) {
  .about-main {
    grid-template-columns: minmax(0, 1fr);
  }

  .floating-card {
    right: 8px;
    bottom: -18px;
  }
}

@media (max-width: 720px) {
  .about-inner {
    padding: 0 16px;
  }

  .about-heading {
    font-size: 24px;
  }

  .about-main {
    gap: 32px;
  }

  .about-image-card img {
    height: 360px;
  }

  .stats-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 480px) {
  .stats-grid {
    grid-template-columns: minmax(0, 1fr);
  }

  .floating-card {
    position: static;
    margin-top: 12px;
  }
}
</style>