<template>
  <!-- Trust Bar — clean white surface strip -->
  <div style="background: #FFFFFF; border-top: 1px solid rgba(0,0,0,0.07); border-bottom: 1px solid rgba(0,0,0,0.07); position: relative; overflow: hidden;">
    <!-- top shimmer line -->
    <div style="position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,rgba(201,168,76,0.5),transparent);"></div>

    <div class="max-w-6xl mx-auto px-4 py-5 sm:py-7">
      <div class="flex flex-wrap items-center justify-center gap-6 md:gap-12 lg:gap-16">
        <div
          v-for="(item, i) in trustItems"
          :key="i"
          class="trust-item gsap-fade-up flex items-center gap-3 group cursor-default"
        >
          <div class="w-10 h-10 rounded-full flex items-center justify-center text-xl flex-shrink-0 transition-all duration-300 group-hover:scale-110"
            style="background: rgba(201,168,76,0.09); border: 1px solid rgba(201,168,76,0.22);">
            {{ item.icon }}
          </div>
          <div>
            <p style="color:#0F1A0A; font-weight:700; font-size:0.9rem; line-height:1.2;">{{ item.label }}</p>
            <p style="color:#9AAD92; font-size:0.72rem; line-height:1.2;" class="hidden sm:block">{{ item.sub }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

const trustItems = [
  { icon: '🫒', label: 'معصور بكرة على البارد',    sub: 'First Cold Press' },
  { icon: '📊', label: 'حموضة أقل من 0.8%',        sub: 'Certified Quality' },
  { icon: '🌿', label: 'طبيعي 100% بدون إضافات',   sub: '100% Natural' },
  { icon: '📍', label: 'من مزارع سيناء الأصيلة',   sub: 'Sinai Origin' },
  { icon: '🤲', label: 'حصاد يدوي بأيدي المزارعين', sub: 'Hand-Picked' },
];

onMounted(() => {
  gsap.to('.trust-item', {
    scrollTrigger: { trigger: '.trust-item', start: 'top 92%' },
    y: 0, opacity: 1, duration: 0.6, stagger: 0.1, ease: 'back.out(1.5)'
  });
});
</script>
