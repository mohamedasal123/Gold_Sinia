<template>
  <section id="why-us" class="section-pad relative overflow-hidden" style="background: #FFFFFF;">
    <!-- Top divider -->
    <div class="section-divider"></div>

    <!-- Subtle decorative blobs (very light) -->
    <div
      style="position:absolute;top:-80px;right:-80px;width:400px;height:400px;border-radius:50%;background:radial-gradient(circle,rgba(201,168,76,0.04) 0%,transparent 70%);pointer-events:none;">
    </div>
    <div
      style="position:absolute;bottom:-80px;left:-80px;width:350px;height:350px;border-radius:50%;background:radial-gradient(circle,rgba(61,122,30,0.05) 0%,transparent 70%);pointer-events:none;">
    </div>

    <div class="max-w-6xl mx-auto px-4 sm:px-6 relative z-10">
      <div class="flex flex-col lg:flex-row items-center gap-12 xl:gap-20">

        <!-- Image -->
        <div class="w-full lg:w-1/2 why-img gsap-slide-right relative">
          <!-- Frame decoration -->
          <div
            style="position:absolute;inset:0;border:1px solid rgba(201,168,76,0.20);border-radius:1.5rem;transform:translate(10px,10px);z-index:-1;">
          </div>
          <div
            style="position:absolute;inset:0;background:linear-gradient(135deg,rgba(61,122,30,0.06),rgba(201,168,76,0.04));border-radius:1.5rem;transform:translate(5px,5px);z-index:-1;filter:blur(6px);">
          </div>

          <div class="relative overflow-hidden h-[480px]"
            style="border-radius:1.5rem; box-shadow: 0 16px 56px rgba(0,0,0,0.12), 0 0 0 1px rgba(201,168,76,0.12);">

            <img src="/assets_v1/poster2.jpeg" alt="مزارع زيتون سيناء"
              class="w-full h-full object-cover object-center block" />

            <!-- Light image overlay tint -->
            <div
              style="position:absolute;inset:0;background:linear-gradient(to top,rgba(0,0,0,0.28) 0%,transparent 55%);">
            </div>

            <div class="absolute top-4 right-4 badge-gold text-xs">🌿 أصالة سيناء</div>
          </div>

          <!-- Stats -->
          <div class="mt-6 grid grid-cols-3 gap-4">
            <div v-for="s in stats" :key="s.label" class="white-card p-4 text-center">
              <div class="text-2xl font-black text-gradient-gold">{{ s.value }}</div>
              <div style="font-size:0.72rem;color:#9AAD92;font-weight:600;margin-top:0.25rem;line-height:1.3;">
                {{ s.label }}
              </div>
            </div>
          </div>
        </div>

        <!-- Text -->
        <div class="w-full lg:w-1/2 why-text gsap-slide-left">
          <span class="section-tag">🫒 قصتنا</span>
          <h2 class="section-title mt-3 mb-6">
            حكاية أصالة<br />
            <span class="text-gradient-gold">من قلب سيناء</span>
          </h2>

          <div class="space-y-4" style="color:#6B7E64;font-size:1rem;line-height:1.8;font-weight:500;">
            <p>في مزارع سيناء الخضراء البكر، حيث الشمس الذهبية والتربة الطيبة، تنمو أشجار الزيتون بعناية فائقة. نحن لا
              نؤمن بالأسرع، بل بالأصح.</p>
            <p>كل زجاجة من "سينا جولد" هي نتاج حصاد يدوي بأيدي مزارعينا، وعصرة أولى على البارد خلال 24 ساعة من القطاف،
              للحفاظ على كامل مغذياتها وطعمها الأصيل.</p>
          </div>

          <!-- Feature rows -->
          <div class="mt-8 space-y-3">
            <div v-for="(f, i) in features" :key="i"
              class="feature-row white-card flex items-start gap-4 p-4 group cursor-default">
              <div
                class="w-10 h-10 rounded-xl flex items-center justify-center text-xl flex-shrink-0 group-hover:scale-110 transition-transform"
                style="background:rgba(61,122,30,0.07);border:1px solid rgba(61,122,30,0.15);">{{ f.icon }}</div>
              <div>
                <h4 style="font-weight:700;color:#0F1A0A;margin-bottom:2px;"
                  class="group-hover:text-[#C9A84C] transition-colors">{{ f.title }}</h4>
                <p style="font-size:0.82rem;color:#9AAD92;">{{ f.desc }}</p>
              </div>
            </div>
          </div>

          <!-- Warning -->
          <div class="mt-6 p-4 rounded-2xl"
            style="background:rgba(201,168,76,0.05);border:1px solid rgba(201,168,76,0.20);">
            <p style="color:#A88935;font-weight:700;font-size:0.88rem;display:flex;gap:0.6rem;align-items:flex-start;">
              <span style="font-size:1.2rem;flex-shrink:0;">⚠️</span>
              لا تشتري زيت مجهول المصدر. سينا جولد مضمون ومصدره من مزارعنا مباشرةً في سيناء.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="section-divider mt-20"></div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

const stats = [
  { value: '+50', label: 'عميل سعيد' },
  { value: '0.8%', label: 'أقصى حموضة' },
  { value: '100%', label: 'طبيعي نقي' },
];
const features = [
  { icon: '❄️', title: 'العصرة الأولى على البارد', desc: 'تحافظ على كل الفيتامينات والبوليفينولات النشطة' },
  { icon: '🤲', title: 'حصاد يدوي 100%', desc: 'لا آلات — كل حبة زيتون بأيدي مزارعينا بعناية' },
  { icon: '📍', title: 'مصدر موثق من سيناء', desc: 'مزارعنا في شبه جزيرة سيناء، مناخ مثالي للزيتون' },
  { icon: '🏆', title: 'جودة معتمدة أقل من 0.8%', desc: 'نسبة الحموضة معيار الجودة الأول عالمياً' },
];

onMounted(() => {
  gsap.to('.why-img', { scrollTrigger: { trigger: '.why-img', start: 'top 80%' }, x: 0, opacity: 1, duration: 0.9, ease: 'power3.out' });
  gsap.to('.why-text', { scrollTrigger: { trigger: '.why-text', start: 'top 80%' }, x: 0, opacity: 1, duration: 0.9, ease: 'power3.out', delay: 0.15 });
  gsap.to('.feature-row', {
    scrollTrigger: { trigger: '.feature-row', start: 'top 85%' },
    y: 0, opacity: 1, duration: 0.5, stagger: 0.1, ease: 'power2.out'
  });
});
</script>
