<template>
  <section id="reviews" class="section-pad relative overflow-hidden" style="background: linear-gradient(180deg, #111a0d 0%, #1a2614 50%, #111a0d 100%);">
    <!-- dot grid -->
    <div style="position:absolute;inset:0;opacity:0.025;pointer-events:none;background-image:radial-gradient(circle at 2px 2px,#C9A84C 1px,transparent 0);background-size:30px 30px;"></div>
    <!-- glow -->
    <div style="position:absolute;top:0;left:50%;transform:translateX(-50%);width:500px;height:300px;background:radial-gradient(ellipse,rgba(201,168,76,0.06) 0%,transparent 70%);pointer-events:none;"></div>

    <div class="max-w-6xl mx-auto px-4 sm:px-6 relative z-10">
      <!-- Header -->
      <div class="text-center mb-16 reviews-header gsap-fade-up">
        <span class="section-tag">⭐ آراء عملائنا</span>
        <h2 class="section-title mt-3 mb-3">رأي عملاؤنا فينا</h2>
        <div class="gold-divider"></div>
        <p class="section-subtitle mx-auto mt-5">مش كلامنا — ده كلام ناس جربت وعاشت الفرق</p>

        <!-- Aggregate rating -->
        <div class="mt-6 inline-flex items-center gap-4 glass-card px-6 py-3" style="border-radius:9999px;">
          <div class="text-3xl font-black text-gradient-gold">4.9</div>
          <div>
            <div class="flex text-[#C9A84C] text-lg leading-none">★★★★★</div>
            <p style="font-size:0.72rem;color:#567048;font-weight:600;margin-top:2px;">بناءً على 500+ تقييم حقيقي</p>
          </div>
        </div>
      </div>

      <!-- Main cards -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div
          v-for="(t, i) in testimonials"
          :key="i"
          class="testimonial-card gsap-fade-up glass-card p-7 flex flex-col"
        >
          <div class="flex text-[#C9A84C] text-base mb-4 leading-none">★★★★★</div>
          <!-- big quote -->
          <div style="position:absolute;top:16px;left:20px;font-size:5rem;color:rgba(201,168,76,0.08);font-family:serif;line-height:1;pointer-events:none;user-select:none;">"</div>

          <p style="color:#8aab78;font-size:0.92rem;line-height:1.75;font-weight:500;flex-grow:1;position:relative;z-index:1;">
            "{{ t.text }}"
          </p>

          <div class="flex items-center gap-3 pt-4 mt-4" style="border-top:1px solid rgba(74,125,37,0.15);">
            <div class="w-11 h-11 rounded-full flex items-center justify-center font-black text-white text-base flex-shrink-0 shadow-lg"
              :style="`background:linear-gradient(135deg,${t.c1},${t.c2})`">{{ t.init }}</div>
            <div class="flex-grow">
              <h4 style="font-weight:800;color:#eef5e8;font-size:0.9rem;">{{ t.name }}</h4>
              <p style="font-size:0.72rem;color:#567048;">{{ t.location }} · {{ t.date }}</p>
            </div>
            <span class="badge-olive text-xs">✓ موثق</span>
          </div>
        </div>
      </div>

      <!-- Mini testimonials -->
      <div class="mt-8 grid grid-cols-1 sm:grid-cols-2 gap-4 mini-cards gsap-fade-up">
        <div v-for="(m, i) in minis" :key="i"
          class="flex items-start gap-3 glass-card p-4">
          <div style="color:#C9A84C;font-size:1.8rem;font-family:serif;flex-shrink:0;line-height:1;">"</div>
          <div>
            <p style="font-size:0.85rem;color:#8aab78;font-weight:500;line-height:1.6;">{{ m.text }}</p>
            <p style="font-size:0.72rem;color:#567048;font-weight:700;margin-top:4px;">— {{ m.name }}, {{ m.loc }}</p>
          </div>
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

const testimonials = [
  { name:'أم كريم', location:'المنصورة، الدقهلية', date:'مارس 2025', init:'أ', c1:'#2D5016', c2:'#4a7d25',
    text:'والله زيت حقيقي زي اللي بنعرفه من زمان. ريحته مش زي اللي في المحلات خالص، وطعمه على السلطة مختلف تماماً. كل أهلي بيطلبوه.' },
  { name:'أبو يوسف', location:'الزقازيق، الشرقية', date:'فبراير 2025', init:'ي', c1:'#C9A84C', c2:'#a88935',
    text:'جربته على السلطة وعلى الجلد بعد النصيحة من الدكتور — وفرق واضح جداً. والدتي بتاخده بدل الكريم على ركبتيها وبتقول مريّح.' },
  { name:'سمر', location:'مدينة نصر، القاهرة', date:'أبريل 2025', init:'س', c1:'#7c3aed', c2:'#9d5df7',
    text:'بعت لأهلي في الريف وكلهم طلبوا تاني. جودة الزجاجة والتغليف محترم، والشحن وصل بسرعة. سينا جولد جزء من مطبخنا دلوقتي.' },
];
const minis = [
  { text:'فعلاً زيت نضيف وطعمه مختلف، من وقتها بقيت بطلب كل شهر.', name:'هالة منير', loc:'الإسكندرية' },
  { text:'جربته لوالدتي والدكاترة نصحوا بزيت طبيعي — الفرق واضح في ضغطها.', name:'محمد عادل', loc:'أسيوط' },
];

onMounted(() => {
  gsap.to('.reviews-header', { scrollTrigger:{trigger:'.reviews-header',start:'top 85%'}, y:0,opacity:1,duration:0.8,ease:'power3.out' });
  gsap.to('.testimonial-card', { scrollTrigger:{trigger:'.testimonial-card',start:'top 85%'}, y:0,opacity:1,duration:0.7,stagger:0.18,ease:'power3.out' });
  gsap.to('.mini-cards', { scrollTrigger:{trigger:'.mini-cards',start:'top 88%'}, y:0,opacity:1,duration:0.7,ease:'power3.out' });
});
</script>
