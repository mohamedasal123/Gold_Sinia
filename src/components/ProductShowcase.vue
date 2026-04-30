<template>
  <section id="products" class="section-pad relative overflow-hidden"
    style="background: linear-gradient(180deg, #1a2614 0%, #0d1509 50%, #111a0d 100%);">

    <!-- BG radial glow -->
    <div style="position:absolute;top:30%;left:50%;transform:translate(-50%,-50%);width:900px;height:600px;border-radius:50%;background:radial-gradient(ellipse,rgba(201,168,76,0.05) 0%,transparent 70%);pointer-events:none;z-index:0;"></div>

    <div class="max-w-6xl mx-auto px-4 sm:px-6 relative z-10">

      <!-- ── Section Header ── -->
      <div class="text-center mb-6 section-hdr gsap-fade-up">
        <span class="section-tag">🛒 الأسعار والعروض</span>
        <h2 class="section-title mt-3 mb-3">اختار حجمك واطلب دلوقتي</h2>
        <div class="gold-divider"></div>
        <p class="section-subtitle mx-auto mt-4">
          زيت سيناء الأصيل بأفضل سعر — العرض لفترة محدودة فقط
        </p>
      </div>

      <!-- ── Scarcity Strip ── -->
      <div class="flex justify-center mb-12 scarcity-strip gsap-fade-up">
        <div class="flex items-center gap-3 px-6 py-3 rounded-full"
          style="background:rgba(239,68,68,0.08);border:1px solid rgba(239,68,68,0.25);backdrop-filter:blur(10px);">
          <span class="w-2.5 h-2.5 rounded-full bg-red-500 flex-shrink-0"
            style="animation:pulse 1.2s ease-in-out infinite;"></span>
          <p style="color:#fca5a5;font-weight:700;font-size:0.88rem;">
            🔥 الكمية محدودة — الطلبات بتتضاعف هذا الأسبوع
          </p>
        </div>
      </div>

      <!-- ── Product Cards Grid ── -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 lg:gap-8 items-start">

        <!-- ─── Card 1: 0.5 لتر ─── -->
        <div class="price-card gsap-fade-up flex flex-col overflow-hidden"
          style="background:rgba(26,38,20,0.65);border:1px solid rgba(74,125,37,0.25);border-radius:1.5rem;backdrop-filter:blur(16px);transition:all 0.35s cubic-bezier(0.4,0,0.2,1);">

          <!-- Top bar -->
          <div style="height:3px;background:linear-gradient(90deg,rgba(74,125,37,0.3),rgba(74,125,37,0.8),rgba(74,125,37,0.3));"></div>

          <!-- Product Image -->
          <div class="relative overflow-hidden" style="height:240px;">
            <img src="/assets_v1/poster1.png" alt="زيت سينا جولد 0.5 لتر"
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105 img-zoom" />
            <!-- image gradient -->
            <div style="position:absolute;inset:0;background:linear-gradient(to top,rgba(13,21,9,0.85) 0%,rgba(13,21,9,0.2) 50%,transparent 100%);"></div>
            <!-- Size label on image -->
            <div style="position:absolute;bottom:14px;right:16px;">
              <span style="background:rgba(13,21,9,0.75);backdrop-filter:blur(8px);border:1px solid rgba(74,125,37,0.4);color:#a8c898;font-weight:800;font-size:0.85rem;padding:0.3rem 0.8rem;border-radius:9999px;">0.5 لتر</span>
            </div>
            <!-- Badge top-left -->
            <div style="position:absolute;top:12px;left:12px;">
              <span style="background:rgba(74,125,37,0.85);backdrop-filter:blur(6px);color:#c8f0a8;font-weight:700;font-size:0.72rem;padding:0.25rem 0.7rem;border-radius:9999px;border:1px solid rgba(74,125,37,0.4);">🌿 مناسب للتجربة</span>
            </div>
          </div>

          <!-- Card Body -->
          <div class="p-6 flex flex-col flex-grow">
            <h3 style="font-size:1.05rem;font-weight:800;color:#eef5e8;margin-bottom:6px;line-height:1.3;">
              زيت زيتون طبيعي 100%
            </h3>
            <p style="font-size:0.8rem;color:#567048;margin-bottom:16px;line-height:1.6;">
              معصور بكرة على البارد · حموضة أقل من 0.8% · من مزارع سيناء
            </p>

            <!-- Features -->
            <ul class="space-y-1.5 mb-5 flex-grow">
              <li v-for="f in features[0]" :key="f" style="font-size:0.8rem;color:#8aab78;font-weight:500;display:flex;align-items:center;gap:0.5rem;">
                <span style="color:#5a9e32;flex-shrink:0;">✓</span>{{ f }}
              </li>
            </ul>

            <!-- Price -->
            <div class="mb-5 p-4 rounded-xl" style="background:rgba(13,21,9,0.5);border:1px solid rgba(74,125,37,0.15);">
              <div style="font-size:0.7rem;color:#567048;font-weight:600;margin-bottom:4px;letter-spacing:0.05em;">السعر</div>
              <div style="display:flex;align-items:flex-end;gap:8px;">
                <span style="font-size:2.4rem;font-weight:900;color:#C9A84C;line-height:1;">320</span>
                <span style="font-size:0.95rem;color:#8aab78;font-weight:600;padding-bottom:5px;">جنيه</span>
              </div>
            </div>

            <!-- CTA -->
            <a href="#order" @click.prevent="order('500ml','300')"
              class="cta-secondary block text-center py-3.5 rounded-xl font-bold"
              style="font-size:0.95rem;">
              اطلب الآن →
            </a>
          </div>
        </div>

        <!-- ─── Card 2: 1 لتر — HERO ─── -->
        <div class="price-card hero-card gsap-fade-up flex flex-col overflow-hidden relative"
          style="background:linear-gradient(170deg,#1f3518 0%,#2c4820 40%,#1a2e14 100%);border:1.5px solid rgba(201,168,76,0.5);border-radius:1.5rem;box-shadow:0 0 50px rgba(201,168,76,0.1),0 20px 60px rgba(0,0,0,0.5);transition:all 0.35s cubic-bezier(0.4,0,0.2,1);">

          <!-- Gold top bar -->
          <div style="height:3px;background:linear-gradient(90deg,#a88935,#C9A84C,#e0c06a,#C9A84C,#a88935);"></div>

          <!-- Best Seller floating badge -->
          <div style="position:absolute;top:0;left:0;right:0;display:flex;justify-content:center;z-index:10;pointer-events:none;">
            <div style="transform:translateY(-50%) translateY(3px);">
              <div style="background:linear-gradient(135deg,#b5922e,#C9A84C,#e0c06a);box-shadow:0 4px 20px rgba(201,168,76,0.5);padding:0.35rem 1.1rem;border-radius:9999px;display:flex;align-items:center;gap:0.4rem;">
                <span style="font-size:0.65rem;">⭐</span>
                <span style="font-size:0.72rem;font-weight:900;color:#fff;letter-spacing:0.05em;white-space:nowrap;">الأكثر مبيعاً — أفضل قيمة</span>
              </div>
            </div>
          </div>

          <!-- Product Image -->
          <div class="relative overflow-hidden" style="height:260px;margin-top:14px;">
            <img src="/assets_v1/poster3.png" alt="زيت سينا جولد 1 لتر"
              class="w-full h-full object-cover img-zoom" style="transition:transform 0.7s ease;" />
            <div style="position:absolute;inset:0;background:linear-gradient(to top,rgba(13,21,9,0.85) 0%,rgba(13,21,9,0.15) 55%,transparent 100%);"></div>
            <!-- Size label -->
            <div style="position:absolute;bottom:14px;right:16px;">
              <span style="background:rgba(201,168,76,0.85);backdrop-filter:blur(8px);color:#fff;font-weight:900;font-size:0.9rem;padding:0.3rem 0.9rem;border-radius:9999px;">1 لتر</span>
            </div>
            <!-- Discount top-left -->
            <div style="position:absolute;top:12px;left:12px;">
              <span style="background:rgba(239,68,68,0.85);backdrop-filter:blur(6px);color:#fff;font-weight:800;font-size:0.72rem;padding:0.25rem 0.7rem;border-radius:9999px;">⏰ عرض لفترة محدودة</span>
            </div>
          </div>

          <!-- Card Body -->
          <div class="p-6 flex flex-col flex-grow">
            <h3 style="font-size:1.15rem;font-weight:900;color:#eef5e8;margin-bottom:6px;line-height:1.3;">
              زيت زيتون بكر ممتاز من سيناء
            </h3>
            <p style="font-size:0.82rem;color:#8aab78;margin-bottom:16px;line-height:1.6;">
              معصور بكرة على البارد · حموضة أقل من 0.8% · يكفي العيلة شهر كامل
            </p>

            <!-- Features -->
            <ul class="space-y-2 mb-5 flex-grow">
              <li v-for="f in features[1]" :key="f" style="font-size:0.82rem;color:#a8c898;font-weight:500;display:flex;align-items:center;gap:0.5rem;">
                <span style="color:#C9A84C;flex-shrink:0;">✓</span>{{ f }}
              </li>
            </ul>

            <!-- Price block -->
            <div class="mb-5 p-4 rounded-xl" style="background:rgba(13,21,9,0.6);border:1px solid rgba(201,168,76,0.2);">
              <div style="font-size:0.7rem;color:#C9A84C;opacity:0.75;font-weight:600;margin-bottom:4px;letter-spacing:0.05em;">السعر بعد الخصم</div>
              <div style="display:flex;align-items:flex-end;gap:10px;flex-wrap:wrap;">
                <span style="font-size:2.8rem;font-weight:900;line-height:1;background:linear-gradient(135deg,#C9A84C,#e0c06a);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">600</span>
                <div style="padding-bottom:6px;">
                  <div style="font-size:1rem;color:#a8c898;font-weight:600;line-height:1;">جنيه</div>
                  <div style="font-size:0.8rem;text-decoration:line-through;color:#567048;line-height:1.4;">640</div>
                </div>
              </div>
              <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:10px;">
                <span style="background:rgba(201,168,76,0.12);border:1px solid rgba(201,168,76,0.3);color:#C9A84C;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">💰 وفرت 40 جنيه</span>
                <span style="background:rgba(239,68,68,0.08);border:1px solid rgba(239,68,68,0.2);color:#fca5a5;font-size:0.72rem;font-weight:700;padding:0.2rem 0.65rem;border-radius:9999px;">عرض خاص</span>
              </div>
            </div>

            <!-- CTA -->
            <a href="#order" @click.prevent="order('1L','580')"
              class="btn-gold block text-center py-4 rounded-xl"
              style="font-size:1rem;font-weight:800;">
              🛒 اطلب الآن — التوصيل لحد بابك
            </a>
            <p style="text-align:center;font-size:0.7rem;color:#567048;margin-top:0.5rem;">الدفع عند الاستلام | توصيل خلال 48 ساعة</p>
          </div>
        </div>

        <!-- ─── Card 3: 3 لتر ─── -->
        <div class="price-card gsap-fade-up flex flex-col overflow-hidden"
          style="background:rgba(26,38,20,0.65);border:1px solid rgba(74,125,37,0.25);border-radius:1.5rem;backdrop-filter:blur(16px);transition:all 0.35s cubic-bezier(0.4,0,0.2,1);">

          <!-- Top bar -->
          <div style="height:3px;background:linear-gradient(90deg,rgba(74,125,37,0.3),rgba(74,125,37,0.8),rgba(74,125,37,0.3));"></div>

          <!-- Product Image -->
          <div class="relative overflow-hidden" style="height:240px;">
            <img src="/assets_v1/poster4.png" alt="زيت سينا جولد 3 لتر"
              class="w-full h-full object-cover img-zoom" style="transition:transform 0.7s ease;" />
            <div style="position:absolute;inset:0;background:linear-gradient(to top,rgba(13,21,9,0.85) 0%,rgba(13,21,9,0.2) 50%,transparent 100%);"></div>
            <!-- Size label -->
            <div style="position:absolute;bottom:14px;right:16px;">
              <span style="background:rgba(13,21,9,0.75);backdrop-filter:blur(8px);border:1px solid rgba(201,168,76,0.35);color:#C9A84C;font-weight:800;font-size:0.85rem;padding:0.3rem 0.8rem;border-radius:9999px;">3 لتر</span>
            </div>
            <!-- Family badge top-left -->
            <div style="position:absolute;top:12px;left:12px;">
              <span style="background:rgba(201,168,76,0.8);backdrop-filter:blur(6px);color:#fff;font-weight:700;font-size:0.72rem;padding:0.25rem 0.7rem;border-radius:9999px;">🏠 خيار العيلة</span>
            </div>
          </div>

          <!-- Card Body -->
          <div class="p-6 flex flex-col flex-grow">
            <h3 style="font-size:1.05rem;font-weight:800;color:#eef5e8;margin-bottom:6px;line-height:1.3;">
              طقم زيت سيناء الفاخر
            </h3>
            <p style="font-size:0.8rem;color:#567048;margin-bottom:16px;line-height:1.6;">
              معصور بكرة على البارد · هدية مثالية أو للعيلة الكبيرة
            </p>

            <!-- Features -->
            <ul class="space-y-1.5 mb-5 flex-grow">
              <li v-for="f in features[2]" :key="f" style="font-size:0.8rem;color:#8aab78;font-weight:500;display:flex;align-items:center;gap:0.5rem;">
                <span style="color:#5a9e32;flex-shrink:0;">✓</span>{{ f }}
              </li>
            </ul>

            <!-- Price block -->
            <div class="mb-5 p-4 rounded-xl" style="background:rgba(13,21,9,0.5);border:1px solid rgba(201,168,76,0.12);">
              <div style="font-size:0.7rem;color:#567048;font-weight:600;margin-bottom:4px;letter-spacing:0.05em;">السعر بعد الخصم</div>
              <div style="display:flex;align-items:flex-end;gap:10px;flex-wrap:wrap;">
                <span style="font-size:2.4rem;font-weight:900;color:#C9A84C;line-height:1;">1800</span>
                <div style="padding-bottom:5px;">
                  <div style="font-size:0.95rem;color:#8aab78;font-weight:600;line-height:1;">جنيه</div>
                  <div style="font-size:0.78rem;text-decoration:line-through;color:#567048;line-height:1.4;">1920</div>
                </div>
              </div>
              <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:10px;">
                <span style="background:rgba(201,168,76,0.08);border:1px solid rgba(201,168,76,0.2);color:#C9A84C;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">💰 وفرت 120 جنيه</span>
                <span style="background:rgba(74,125,37,0.08);border:1px solid rgba(74,125,37,0.2);color:#5a9e32;font-size:0.72rem;font-weight:700;padding:0.2rem 0.65rem;border-radius:9999px;">🎁 هدية مميزة</span>
              </div>
            </div>

            <!-- CTA -->
            <a href="#order" @click.prevent="order('3L','1700')"
              class="cta-secondary block text-center py-3.5 rounded-xl font-bold"
              style="font-size:0.95rem;">
              اطلب الطقم الآن →
            </a>
          </div>
        </div>

      </div><!-- /grid -->

      <!-- ── Value Props Strip ── -->
      <div class="mt-10 value-strip gsap-fade-up">
        <div class="glass-card p-6 md:p-8">
          <div class="grid grid-cols-1 sm:grid-cols-3 gap-6 text-center">
            <div v-for="v in valueProps" :key="v.title" class="flex flex-col items-center gap-2">
              <div style="font-size:2rem;">{{ v.icon }}</div>
              <h4 style="font-weight:800;color:#eef5e8;font-size:0.9rem;">{{ v.title }}</h4>
              <p style="font-size:0.78rem;color:#567048;line-height:1.5;">{{ v.desc }}</p>
            </div>
          </div>
        </div>
      </div>

      <!-- ── Final CTA ── -->
      <div class="mt-8 text-center final-cta gsap-fade-up">
        <p style="color:#567048;font-size:0.85rem;margin-bottom:1rem;">
          ⚡ السعر ممكن يتغير — اطلب دلوقتي وضمن سعر العرض
        </p>
        <a href="#order" @click.prevent="scrollTo('order')" class="btn-gold text-lg px-10 py-4 rounded-full">
          🛒 اطلب الآن — الدفع عند الاستلام
        </a>
        <div style="display:flex;align-items:center;justify-content:center;gap:1.5rem;margin-top:1rem;flex-wrap:wrap;">
          <span v-for="g in guarantees" :key="g" style="font-size:0.75rem;color:#567048;font-weight:600;display:flex;align-items:center;gap:0.25rem;">{{ g }}</span>
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

const scrollTo = (id) => document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });

const order = (size, price) => {
  scrollTo('order');
  window.dispatchEvent(new CustomEvent('select-product', { detail: { size, price } }));
};

const features = [
  // 0.5L
  ['زيت بكر ممتاز من مزارع سيناء', 'معصور بكرة على البارد', 'حموضة أقل من 0.8%', 'مثالي للتجربة والتذوق'],
  // 1L
  ['زيت بكر ممتاز من مزارع سيناء', 'معصور بكرة على البارد', 'حموضة أقل من 0.8%', 'يكفي العيلة شهر كامل', 'توفير 20 جنيه عن السعر العادي'],
  // 3L
  ['زيت بكر ممتاز من مزارع سيناء', 'معصور بكرة على البارد', 'حموضة أقل من 0.8%', 'توفير 100 جنيه من السعر الأصلي', 'مثالي للهدايا والعيلة الكبيرة'],
];

const valueProps = [
  { icon: '🌿', title: 'طبيعي 100% من سيناء',       desc: 'لا إضافات كيميائية — مباشر من المزرعة لمائدتك' },
  { icon: '🏆', title: 'أفضل سعر مضمون',             desc: 'لو لقيت أرخص بنفس الجودة هنرد عليك الفرق' },
  { icon: '🚚', title: 'توصيل 48 ساعة لكل مصر',      desc: 'الدفع عند الاستلام — مش محتاج تدفع قبل ما تشوف المنتج' },
];

const guarantees = ['✓ دفع عند الاستلام', '✓ ضمان الجودة', '✓ توصيل لكل المحافظات'];

onMounted(() => {
  gsap.to('.section-hdr', {
    scrollTrigger: { trigger: '.section-hdr', start: 'top 85%' },
    y: 0, opacity: 1, duration: 0.8, ease: 'power3.out'
  });
  gsap.to('.scarcity-strip', {
    scrollTrigger: { trigger: '.scarcity-strip', start: 'top 88%' },
    y: 0, opacity: 1, duration: 0.6, delay: 0.15, ease: 'power2.out'
  });
  gsap.to('.price-card', {
    scrollTrigger: { trigger: '.price-card', start: 'top 85%' },
    y: 0, opacity: 1, duration: 0.7, stagger: 0.15, ease: 'power3.out'
  });
  gsap.to('.value-strip', {
    scrollTrigger: { trigger: '.value-strip', start: 'top 90%' },
    y: 0, opacity: 1, duration: 0.7, ease: 'power3.out'
  });
  gsap.to('.final-cta', {
    scrollTrigger: { trigger: '.final-cta', start: 'top 92%' },
    y: 0, opacity: 1, duration: 0.7, ease: 'power3.out'
  });

  // Image parallax zoom on hover
  document.querySelectorAll('.price-card').forEach(card => {
    const img = card.querySelector('.img-zoom');
    if (!img) return;
    card.addEventListener('mouseenter', () => gsap.to(img, { scale: 1.07, duration: 0.6, ease: 'power2.out' }));
    card.addEventListener('mouseleave', () => gsap.to(img, { scale: 1,    duration: 0.6, ease: 'power2.out' }));
  });
});
</script>

<style scoped>
/* ── Standard card hover ── */
.price-card:hover {
  border-color: rgba(201,168,76,0.4) !important;
  box-shadow: 0 20px 60px rgba(0,0,0,0.55), 0 0 30px rgba(201,168,76,0.1) !important;
  transform: translateY(-7px) !important;
}

/* ── Hero card hover ── */
.hero-card {
  transform: scale(1.03);
}
.hero-card:hover {
  transform: scale(1.05) translateY(-7px) !important;
  box-shadow: 0 30px 80px rgba(0,0,0,0.65), 0 0 50px rgba(201,168,76,0.22) !important;
  border-color: rgba(201,168,76,0.7) !important;
}

/* ── Secondary CTA ── */
.cta-secondary {
  background: rgba(74,125,37,0.1);
  border: 1.5px solid rgba(74,125,37,0.35);
  color: #a8c898;
  font-family: 'Cairo', sans-serif;
  cursor: pointer;
  text-decoration: none;
  transition: all 0.25s ease;
}
.cta-secondary:hover {
  background: rgba(74,125,37,0.2);
  border-color: rgba(201,168,76,0.4);
  color: #eef5e8;
  transform: translateY(-1px);
}

/* Mobile: reset hero card scale */
@media (max-width: 768px) {
  .hero-card { transform: scale(1) !important; }
  .hero-card:hover { transform: translateY(-5px) !important; }
}
</style>
