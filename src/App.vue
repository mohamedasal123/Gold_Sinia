<template>
  <div style="background:#FFFFFF; min-height:100vh; color:#0F1A0A;">
    <!-- Floating olive layer (very subtle on white) -->
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
