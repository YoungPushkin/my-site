<template>
  <section id="reviews" class="testimonials-section">
    <div class="decor decor-1"></div>
    <div class="decor decor-2"></div>

    <div class="container">
      <div class="header">
        <div class="pill"><span>Testimonials</span></div>
        <h2 class="title">What Our Clients Say</h2>
        <p class="subtitle">
          Don't just take our word for it. Here's what our valued customers have to say about their experiences.
        </p>
      </div>

      <div class="cards-grid">
        <div
          v-for="(t, i) in testimonials"
          :key="i"
          class="card"
        >
          <div class="quote-icon">❝</div>

          <div class="rating">
            <span v-for="n in t.rating" :key="n" class="star">★</span>
          </div>

          <p class="text">"{{ t.text }}"</p>

          <div class="author">
            <div class="avatar">
              {{ initials(t.name) }}
            </div>
            <div>
              <div class="author-name">{{ t.name }}</div>
              <div class="author-role">{{ t.role }}</div>
            </div>
          </div>
        </div>
      </div>

      <div class="stats-block">
        <div class="stats-decor stats-decor-1"></div>
        <div class="stats-decor stats-decor-2"></div>

        <h3 class="stats-title">Trusted by Thousands</h3>
        <div class="stats-grid">
          <div
            v-for="(s, i) in stats"
            :key="i"
            class="stat-item"
          >
            <div class="stat-number">{{ s.number }}</div>
            <div class="stat-label">{{ s.label }}</div>
          </div>
        </div>
      </div>

      <div class="badge-row">
      
      </div>
    </div>
  </section>
</template>

<script setup>
const testimonials = [
  {
    name: 'Sarah Mitchell',
    role: 'Wedding Coordinator',
    text: 'Absolutely exceptional service! The charter bus for our wedding guests was immaculate, and the driver was incredibly professional. Everyone arrived relaxed and on time. Highly recommended!',
    rating: 5,
  },
  {
    name: 'James Patterson',
    role: 'Corporate Event Manager',
    text: 'We use them for all our corporate events. The vehicles are always pristine, drivers are punctual, and their customer service team goes above and beyond. A true partner for our business.',
    rating: 5,
  },
  {
    name: 'Linda Chen',
    role: 'Tour Organizer',
    text: 'The wine country tour was unforgettable! Comfortable seating, smooth ride, and our driver shared wonderful local insights. This is how group travel should be done.',
    rating: 5,
  },
]

const stats = [
  { number: '50,000+', label: 'Happy Customers' },
  { number: '25+', label: 'Years in Business' },
  { number: '99.8%', label: 'On-Time Rate' },
  { number: '5,000+', label: 'Successful Events' },
]

const trustBadges = ['Licensed & Insured', 'DOT Certified', 'Safety First', 'BBB Accredited']

function initials(name) {
  return name
    .split(' ')
    .map((n) => n[0])
    .join('')
}
</script>

<style scoped>
.testimonials-section {
  position: relative;
  padding: 90px 0;
  background: linear-gradient(to bottom, #f5f0e880, #ffffff);
  overflow: hidden;
}

.decor {
  position: absolute;
  border-radius: 999px;
  filter: blur(80px);
  opacity: 0.4;
}
.decor-1 {
  width: 280px;
  height: 280px;
  background: #c4954a1a;
  top: 80px;
  right: 80px;
}
.decor-2 {
  width: 360px;
  height: 360px;
  background: #d4a76a1a;
  bottom: 80px;
  left: 80px;
}

.container {
  position: relative;
  z-index: 5;
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 16px;
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
  max-width: 600px;
  margin: 0 auto;
  color: #6b5744;
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 24px;
  margin-bottom: 60px;
}

.card {
  position: relative;
  background: #ffffff;
  border-radius: 26px;
  padding: 30px 24px 24px;
  border: 1px solid rgba(196, 149, 74, 0.18);
  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.08);
  transition: 0.3s ease;
}
.card:hover {
  box-shadow: 0 22px 60px rgba(0, 0, 0, 0.12);
  transform: translateY(-4px);
}

.quote-icon {
  position: absolute;
  top: -16px;
  left: -16px;
  width: 48px;
  height: 48px;
  border-radius: 18px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  color: #ffffff;
  font-size: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.25);
}

.rating {
  display: flex;
  gap: 4px;
  margin-bottom: 10px;
}
.star {
  font-size: 18px;
  color: #c4954a;
}

.text {
  color: #6b5744;
  font-size: 14px;
  line-height: 1.6;
  margin-bottom: 18px;
  font-style: italic;
}

.author {
  display: flex;
  align-items: center;
  gap: 12px;
  padding-top: 12px;
  border-top: 1px solid rgba(196, 149, 74, 0.18);
}

.avatar {
  width: 46px;
  height: 46px;
  border-radius: 999px;
  background: linear-gradient(to bottom right, #c4954a, #d4a76a);
  color: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
}

.author-name {
  color: #3e342b;
  font-size: 15px;
}
.author-role {
  color: #6b5744;
  font-size: 13px;
}

.stats-block {
  position: relative;
  margin-bottom: 40px;
  padding: 42px 26px;
  border-radius: 26px;
  background: linear-gradient(to bottom right, #3e342b, #6b5744);
  color: #ffffff;
  overflow: hidden;
  box-shadow: 0 22px 60px rgba(0, 0, 0, 0.2);
}

.stats-decor {
  position: absolute;
  border-radius: 999px;
  filter: blur(90px);
  opacity: 0.18;
}
.stats-decor-1 {
  width: 260px;
  height: 260px;
  background: #c4954a;
  top: -40px;
  right: -30px;
}
.stats-decor-2 {
  width: 300px;
  height: 300px;
  background: #d4a76a;
  bottom: -60px;
  left: -40px;
}

.stats-title {
  position: relative;
  z-index: 2;
  text-align: center;
  font-size: 22px;
  margin-bottom: 26px;
}

.stats-grid {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 20px;
}

.stat-item {
  text-align: center;
}

.stat-number {
  color: #c4954a;
  font-weight: 600;
  margin-bottom: 4px;
}
.stat-label {
  color: #ffffffd0;
  font-size: 14px;
}



@media (max-width: 768px) {
  .cards-grid {
    grid-template-columns: 1fr;
  }
  .stats-block {
    padding: 34px 20px;
  }
}
</style>