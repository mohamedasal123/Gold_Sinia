<template>
  <section id="benefits" class="section-pad relative overflow-hidden" style="background: #F8F9FA;">

    <div class="max-w-6xl mx-auto px-4 sm:px-6 relative z-10">
      <!-- Header -->
      <div class="text-center mb-16 benefits-header gsap-fade-up">
        <span class="section-tag">💡 الفوائد الصحية</span>
        <h2 class="section-title mt-3 mb-3">ليه زيت جولد سيناء؟</h2>
        <div class="gold-divider"></div>
        <p class="section-subtitle mx-auto mt-5">
          زيت زيتون سيناء مش بس طعام — هو استثمار في صحتك وصحة عيلتك
        </p>
      </div>

      <!-- Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(b, i) in benefits"
          :key="i"
          class="benefit-card white-card p-7 group cursor-default"
        >
          <div class="w-14 h-14 rounded-xl flex items-center justify-center text-3xl mb-5 transition-all duration-300 group-hover:scale-110 group-hover:-rotate-3"
            :style="`background: ${b.bg};`">{{ b.icon }}</div>
          <h3 class="text-lg font-extrabold mb-2 transition-colors duration-200 group-hover:text-[#C9A84C]" style="color:#0F1A0A;">
            {{ b.title }}</h3>
          <p style="color:#6B7E64; font-size:0.88rem; line-height:1.7;">{{ b.desc }}</p>
          <!-- animated underline -->
          <div class="mt-5 h-px w-0 group-hover:w-full transition-all duration-500 rounded-full"
            style="background: linear-gradient(90deg, #3D7A1E, #C9A84C);"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

const benefits = [
  { icon:'🫀', title:'يحمي القلب والشرايين',
    desc:'غني بحمض الأوليك والبوليفينولات اللي تقلل الكوليسترول الضار وتقوي جدار الأوعية الدموية.',
    bg:'rgba(239,68,68,0.07)' },
  { icon:'🧠', title:'يقوي الدماغ والذاكرة',
    desc:'أوميجا 9 ومضادات الأكسدة بتحمي الخلايا العصبية وبتحسن التركيز والذاكرة بشكل ملحوظ.',
    bg:'rgba(99,102,241,0.07)' },
  { icon:'🦴', title:'يدعم صحة العظام',
    desc:'يساعد على امتصاص فيتامين د والكالسيوم ويقلل الالتهابات المفصلية خصوصاً عند كبار السن.',
    bg:'rgba(245,158,11,0.08)' },
  { icon:'✨', title:'للبشرة والشعر الصحي',
    desc:'فيتامين E وسكوالين طبيعي يرطبوا البشرة بعمق ويقووا بصيلات الشعر ويمنعوا تساقطه.',
    bg:'rgba(236,72,153,0.07)' },
  { icon:'💪', title:'يرفع المناعة',
    desc:'مضادات الالتهاب الطبيعية كالأوليوكانثال تحارب البكتيريا والفيروسات وتقوي المناعة.',
    bg:'rgba(16,185,129,0.07)' },
  { icon:'🥗', title:'طعم أصيل لا مثيل له',
    desc:'نكهة سيناوية غنية لا تقارن بالزيت المصنع — فرق واضح في الأكل والسلطة والطبخ.',
    bg:'rgba(61,122,30,0.08)' },
];

onMounted(() => {
  gsap.to('.benefits-header', {
    scrollTrigger: { trigger: '.benefits-header', start: 'top 85%' },
    y: 0, opacity: 1, duration: 0.8, ease: 'power3.out'
  });
  gsap.to('.benefit-card', {
    scrollTrigger: { trigger: '.benefit-card', start: 'top 85%' },
    scale: 1, opacity: 1, duration: 0.6, stagger: 0.1, ease: 'back.out(1.3)'
  });
});
</script>
