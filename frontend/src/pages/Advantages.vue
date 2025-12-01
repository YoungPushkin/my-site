<template>
  <section id="advantages" class="advantages-section">
    <div class="decor decor-1"></div>
    <div class="decor decor-2"></div>

    <div class="container">
      <div class="header">
        <div class="pill"><span>Why Choose Us</span></div>

        <h2 class="title">Your Comfort and Safety Are Our Priority</h2>

        <p class="subtitle">
          We combine modern technology, professional expertise, and genuine care to deliver 
          exceptional transportation experiences every time.
        </p>
      </div>

      <div class="advantages-grid">
        <div 
          v-for="(adv, i) in advantages"
          :key="i"
          class="adv-card"
        >
          <div class="icon" :style="iconGradient(adv.gradient)">
            {{ adv.icon }}
          </div>

          <h3 class="adv-title">{{ adv.title }}</h3>

          <p class="adv-desc">{{ adv.description }}</p>

          <div class="corner"></div>
        </div>
      </div>

      <div class="cta">
        <div class="cta-bg-1"></div>
        <div class="cta-bg-2"></div>

        <h3 class="cta-title">Ready to Experience the Difference?</h3>

        <p class="cta-sub">
          Join thousands of satisfied customers who trust us for their transportation needs. 
          Book your journey today and travel with confidence.
        </p>

        <div class="cta-buttons">
          <button class="cta-main">Get a Free Quote</button>
          <button class="cta-secondary">View Our Fleet</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const advantages = [
  {
    icon: "✔️",
    title: "Modern, Well-Maintained Fleet",
    description:
      "All vehicles undergo regular inspections and maintenance. We invest in the latest models with enhanced safety features and premium comfort.",
    gradient: ["#C4954A", "#D4A76A"],
  },
  {
    icon: "👤",
    title: "Experienced, Polite Drivers",
    description:
      "Our professional drivers are carefully selected, fully licensed, and trained in customer service excellence and defensive driving.",
    gradient: ["#D4A76A", "#C4954A"],
  },
  {
    icon: "🛡️",
    title: "Uncompromising Safety Standards",
    description:
      "DOT certified, fully insured, GPS-tracked vehicles. We exceed industry safety requirements to protect every passenger.",
    gradient: ["#C4954A", "#D4A76A"],
  },
  {
    icon: "🛋️",
    title: "Comfortable Interiors",
    description:
      "Climate-controlled cabins, reclining seats, ample legroom, and modern entertainment systems for a pleasant journey.",
    gradient: ["#D4A76A", "#C4954A"],
  },
  {
    icon: "⏱️",
    title: "Fast & Easy Booking",
    description:
      "24/7 online booking, instant confirmation, flexible scheduling, and quick response via phone, email, or messenger apps.",
    gradient: ["#C4954A", "#D4A76A"],
  },
  {
    icon: "💲",
    title: "Transparent, Fair Pricing",
    description:
      "No hidden fees, clear quotes upfront, competitive rates, and flexible payment options. Quality service at honest prices.",
    gradient: ["#D4A76A", "#C4954A"],
  },
]

function iconGradient(arr) {
  return `background: linear-gradient(to bottom right, ${arr[0]}, ${arr[1]})`
}
</script>

<style scoped>.advantages-section {
  padding: 90px 0;
  background: linear-gradient(to bottom, #ffffff, #f5f0e880);
  position: relative;
  overflow: hidden;
}

.decor {
  position: absolute;
  width: 420px;
  height: 420px;
  border-radius: 999px;
  filter: blur(80px);
  opacity: 0.3;
}
.decor-1 {
  background: #c4954a1a;
  top: 70px;
  left: 60px;
}
.decor-2 {
  background: #d4a76a1a;
  bottom: 80px;
  right: 60px;
}

.container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 16px;
  position: relative;
  z-index: 5;
}

.header {
  text-align: center;
  margin-bottom: 50px;
}

.pill {
  display: inline-block;
  padding: 10px 26px;
  border-radius: 999px;
  border: 1px solid rgba(196, 149, 74, 0.25);
  background: linear-gradient(
    to right,
    #c4954a1a,
    #d4a76a1a
  );
  margin-bottom: 16px;
}
.pill span {
  color: #c4954a;
}

.title {
  color: #3e342b;
  font-size: 28px;
  margin-bottom: 12px;
}

.subtitle {
  max-width: 700px;
  margin: 0 auto;
  color: #6b5744;
  font-size: 17px;
}

.advantages-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(330px, 1fr));
  gap: 26px;
}

.adv-card {
  background: white;
  padding: 32px;
  border-radius: 28px;
  border: 1px solid rgba(196, 149, 74, 0.15);
  box-shadow: 0 16px 40px rgba(0,0,0,0.08);
  position: relative;
  transition: 0.4s ease;
}
.adv-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 22px 60px rgba(0,0,0,0.12);
}

.icon {
  width: 74px;
  height: 74px;
  border-radius: 22px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-size: 34px;
  margin-bottom: 20px;
  box-shadow: 0 14px 30px rgba(0,0,0,0.15);
  transition: transform 0.3s ease;
}
.adv-card:hover .icon {
  transform: scale(1.1);
}

.adv-title {
  font-size: 20px;
  color: #3e342b;
  margin-bottom: 10px;
}

.adv-desc {
  color: #6b5744;
  font-size: 15px;
  line-height: 1.55;
}

.corner {
  position: absolute;
  top: 0;
  right: 0;
  width: 110px;
  height: 110px;
  background: linear-gradient(to bottom right, #c4954a0d, transparent);
  border-bottom-left-radius: 100%;
}

.cta {
  margin-top: 60px;
  background: linear-gradient(to bottom right, #3e342b, #6b5744);
  border-radius: 28px;
  padding: 60px 24px;
  position: relative;
  color: white;
  overflow: hidden;
}

.cta-bg-1,
.cta-bg-2 {
  position: absolute;
  width: 360px;
  height: 360px;
  border-radius: 999px;
  filter: blur(90px);
  opacity: 0.15;
}
.cta-bg-1 {
  background: #c4954a;
  top: 0;
  right: 0;
}
.cta-bg-2 {
  background: #d4a76a;
  bottom: 0;
  left: 0;
}

.cta-title {
  text-align: center;
  font-size: 26px;
  margin-bottom: 14px;
}

.cta-sub {
  text-align: center;
  max-width: 680px;
  margin: 0 auto 26px;
  font-size: 17px;
  color: #ffffffd0;
}

.cta-buttons {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
}

.cta-main {
  padding: 14px 32px;
  border-radius: 999px;
  background: linear-gradient(to right, #c4954a, #d4a76a);
  border: none;
  color: white;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 12px 30px rgba(0,0,0,0.25);
  transition: 0.3s ease;
}
.cta-main:hover {
  transform: translateY(-2px);
  box-shadow: 0 16px 40px rgba(0,0,0,0.32);
}

.cta-secondary {
  padding: 14px 32px;
  border-radius: 999px;
  background: rgba(255,255,255,0.1);
  border: 2px solid rgba(255,255,255,0.3);
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s ease;
}
.cta-secondary:hover {
  background: rgba(255,255,255,0.2);
  border-color: white;
}
</style>