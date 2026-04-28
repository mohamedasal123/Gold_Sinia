<template>
  <div style="background:#0d1509; min-height:100vh; color:#eef5e8;">
    <!-- Noise texture -->
    <div class="noise-overlay"></div>
    <!-- Floating olive layer -->
    <FloatingOlives />

    <Navbar />
    <main style="position:relative; z-index:2;">
      <HeroSection />
      <TrustBar />
      <BenefitsSection />
      <WhySinaGold />
      <ProductShowcase />
      <!-- <TestimonialsSection /> -->
      <ContactForm />
      <FooterSection />
    </main>
    <FloatingElements />
  </div>
</template>

<script setup>
import Navbar            from './components/Navbar.vue';
import HeroSection       from './components/HeroSection.vue';
import TrustBar          from './components/TrustBar.vue';
import BenefitsSection   from './components/BenefitsSection.vue';
import WhySinaGold       from './components/WhySinaGold.vue';
import ProductShowcase   from './components/ProductShowcase.vue';
import TestimonialsSection from './components/TestimonialsSection.vue';
import ContactForm       from './components/ContactForm.vue';
import FooterSection     from './components/FooterSection.vue';
import FloatingElements  from './components/FloatingElements.vue';
import FloatingOlives    from './components/FloatingOlives.vue';
</script>
