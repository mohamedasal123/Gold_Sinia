<template>
  <section id="products" class="section-pad relative overflow-hidden"
    style="background: #ffffff;">

    <div style="position:absolute;top:30%;left:50%;transform:translate(-50%,-50%);width:900px;height:600px;border-radius:50%;background:radial-gradient(ellipse,rgba(214,181,92,0.15) 0%,transparent 70%);pointer-events:none;z-index:0;"></div>

    <div class="max-w-6xl mx-auto px-4 sm:px-6 relative z-10">

      <div class="text-center mb-6 section-hdr gsap-fade-up">
        <span class="section-tag" style="color: #1a2614; font-weight: 700;">🛒 الأسعار والعروض</span>
        <h2 class="section-title mt-3 mb-3" style="color: #1a2614;">اختار حجمك واطلب دلوقتي</h2>
        <div class="gold-divider" style="background: #d6b55c;"></div>
        <p class="section-subtitle mx-auto mt-4" style="color: #4a5568;">
          زيت سيناء الأصيل بأفضل سعر — العرض لفترة محدودة فقط
        </p>
      </div>

      <div class="flex justify-center mb-6 scarcity-strip gsap-fade-up">
        <div class="flex items-center gap-3 px-6 py-3 rounded-full"
          style="background:rgba(239,68,68,0.08);border:1px solid rgba(239,68,68,0.25);backdrop-filter:blur(10px);">
          <span class="w-2.5 h-2.5 rounded-full bg-red-500 flex-shrink-0"
            style="animation:pulse 1.2s ease-in-out infinite;"></span>
          <p style="color:#ef4444;font-weight:700;font-size:0.88rem;">
            🔥 الكمية محدودة — الطلبات بتتضاعف هذا الأسبوع
          </p>
        </div>
      </div>

      <div class="discount-banner gsap-fade-up mb-12">
        <div style="position:relative;border-radius:1.25rem;overflow:hidden;">
          <div class="banner-glow-border"></div>
          <div style="
            position:relative;z-index:1;
            background:linear-gradient(135deg,rgba(20,10,0,0.92) 0%,rgba(35,20,5,0.95) 50%,rgba(20,10,0,0.92) 100%);
            border-radius:1.2rem;
            margin:2px;
            padding:1.5rem 1.75rem;
          ">
            <div style="display:flex;align-items:center;justify-content:center;gap:0.75rem;flex-wrap:wrap;margin-bottom:1.1rem;">
              <span style="
                background:linear-gradient(135deg,#b5442e,#e05535,#ff6b4a);
                color:#fff;font-weight:900;font-size:0.8rem;
                padding:0.3rem 0.85rem;border-radius:9999px;
                box-shadow:0 0 16px rgba(224,85,53,0.5);
                white-space:nowrap;
              ">⚡ اليوم فقط</span>
              <h3 style="
                font-size:clamp(1.25rem,3.5vw,1.7rem);
                font-weight:900;
                background:linear-gradient(135deg,#ffb347,#ffd700,#d6b55c);
                -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
                line-height:1.2;text-align:center;
              ">🎁 خصم 15% إضافي على كل الأحجام</h3>
            </div>
            <div style="height:1px;background:linear-gradient(90deg,transparent,rgba(214,181,92,0.3),transparent);margin-bottom:1.1rem;"></div>
            <div style="text-align:center;margin-bottom:0.7rem;">
              <p style="font-size:1.5rem;font-weight:600;color:#d6b55c;font-weight:600;letter-spacing:0.08em;margin-bottom:0.75rem;">
                ⏳ العرض ينتهي بعد
              </p>
              <div style="display:flex;align-items:center;justify-content:center;gap:0.6rem;flex-wrap:wrap;">
                <div class="timer-block">
                  <span class="timer-digit">{{ pad(timer.hours) }}</span>
                  <span class="timer-label">ساعة</span>
                </div>
                <span class="timer-colon">:</span>
                <div class="timer-block">
                  <span class="timer-digit">{{ pad(timer.minutes) }}</span>
                  <span class="timer-label">دقيقة</span>
                </div>
                <span class="timer-colon">:</span>
                <div class="timer-block timer-block--sec">
                  <span class="timer-digit">{{ pad(timer.seconds) }}</span>
                  <span class="timer-label">ثانية</span>
                </div>
              </div>
            </div>
            <p style="text-align:center;font-size:0.73rem;color:#b08b5c;margin-top:0.75rem;font-weight:600;">
              🔒 الخصم تلقائي — مش محتاج كود — بس لحد منتصف الليل
            </p>
          </div>
        </div>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 lg:gap-8 items-start">

        <div class="price-card gsap-fade-up flex flex-col overflow-hidden"
          style="background: linear-gradient(145deg, #dfbc62 0%, #d1ab4e 100%); border:1px solid rgba(255,255,255,0.6);border-radius:1.5rem;box-shadow:0 15px 35px rgba(214,181,92,0.2);transition:all 0.35s cubic-bezier(0.4,0,0.2,1);">

          <div style="height:3px;background:rgba(255,255,255,0.5);"></div>

          <div class="relative overflow-hidden" style="height:240px;">
            <img src="/assets_v1/poster1.png" alt="زيت سينا جولد 0.5 لتر"
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105 img-zoom" />
            <div style="position:absolute;inset:0;background:linear-gradient(to top, #d1ab4e 0%, rgba(209,171,78,0.1) 50%, transparent 100%);"></div>
            <div style="position:absolute;bottom:14px;right:16px;">
              <span style="background:rgba(255,255,255,0.9);backdrop-filter:blur(8px);border:1px solid rgba(255,255,255,0.4);color:#a3802e;font-weight:900;font-size:0.85rem;padding:0.3rem 0.8rem;border-radius:9999px;box-shadow:0 4px 10px rgba(0,0,0,0.05);">0.5 لتر</span>
            </div>
            <div style="position:absolute;top:12px;left:12px;">
              <span style="background:rgba(26,38,20,0.85);backdrop-filter:blur(6px);color:#fff;font-weight:700;font-size:0.72rem;padding:0.25rem 0.7rem;border-radius:9999px;border:1px solid rgba(255,255,255,0.2);">🌿 مناسب للتجربة</span>
            </div>
            <div style="position:absolute;top:12px;right:12px;">
              <span style="
                background:linear-gradient(135deg,rgba(224,85,53,0.9),rgba(185,50,30,0.9));
                backdrop-filter:blur(6px);color:#fff;font-weight:900;font-size:0.7rem;
                padding:0.25rem 0.65rem;border-radius:9999px;
                box-shadow:0 0 10px rgba(224,85,53,0.4);
              ">خصم 15%</span>
            </div>
          </div>

          <div class="p-6 flex flex-col flex-grow">
            <h3 style="font-size:1.05rem;font-weight:900;color:#1a2614;margin-bottom:6px;line-height:1.3;">
              زيت زيتون طبيعي 100%
            </h3>
            <p style="font-size:0.8rem;color:#3e4f35;margin-bottom:16px;line-height:1.6;font-weight:600;">
              معصور بكرة على البارد · حموضة أقل من 0.8% · من مزارع سيناء
            </p>

            <!-- <ul class="space-y-1.5 mb-5 flex-grow">
              <li v-for="f in features[0]" :key="f" style="font-size:0.8rem;color:#1a2614;font-weight:700;display:flex;align-items:center;gap:0.5rem;">
                <span style="color:#ffffff;background:#1a2614;border-radius:50%;width:16px;height:16px;display:flex;align-items:center;justify-content:center;font-size:0.6rem;flex-shrink:0;">✓</span>{{ f }}
              </li>
            </ul> -->

            <div class="mb-5 p-4 rounded-xl" style="background:rgba(255,255,255,0.4);border:1px solid rgba(255,255,255,0.7);">
              <div style="font-size:0.7rem;color:#3e4f35;font-weight:800;margin-bottom:4px;letter-spacing:0.05em;">السعر بعد خصم اليوم</div>
              <div style="display:flex;align-items:flex-end;gap:8px;flex-wrap:wrap;">
                <span style="font-size:2.4rem;font-weight:900;color:#1a2614;line-height:1;">300</span>
                <div style="padding-bottom:5px;">
                  <div style="font-size:0.95rem;color:#1a2614;font-weight:800;line-height:1;">جنيه</div>
                  <div style="font-size:1.5rem;font-weight:600;text-decoration:line-through;color:#b9321e;line-height:1.4;">320</div>
                </div>
              </div>
              <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:10px;">
                <span style="background:rgba(255,255,255,0.8);border:1px solid rgba(255,255,255,1);color:#1a2614;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">💰 وفرت 20 جنيه</span>
                <span style="background:rgba(224,85,53,0.15);border:1px solid rgba(224,85,53,0.3);color:#b9321e;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">⚡ اليوم فقط</span>
              </div>
            </div>

            <a href="#order" @click.prevent="order('500ml','272')"
              class="cta-secondary block text-center py-3.5 rounded-xl font-bold"
              style="font-size:0.95rem;">
              اطلب الآن →
            </a>
          </div>
        </div>

        <div class="price-card hero-card gsap-fade-up flex flex-col relative"
          style="background: linear-gradient(145deg, #dfbc62 0%, #d1ab4e 100%); border:1.5px solid #ffffff;border-radius:1.5rem;box-shadow:0 20px 50px rgba(214,181,92,0.3);transition:all 0.35s cubic-bezier(0.4,0,0.2,1);margin-top:18px;">

          <div style="position:absolute;top:0;left:0;right:0;display:flex;justify-content:center;z-index:10;pointer-events:none;">
            <div style="transform:translateY(-50%);background:#1a2614;box-shadow:0 4px 20px rgba(0,0,0,0.2);padding:0.35rem 1.1rem;border-radius:9999px;border:1px solid rgba(214,181,92,0.8);display:flex;align-items:center;gap:0.4rem;">
              <span style="font-size:0.65rem;">⭐</span>
              <span style="font-size:0.72rem;font-weight:900;color:#fff;letter-spacing:0.05em;white-space:nowrap;">الأكثر مبيعاً — أفضل قيمة</span>
            </div>
          </div>

          <div class="relative overflow-hidden" style="height:260px;border-radius:1.4rem 1.4rem 0 0;">
            <img src="/assets_v1/poster3.png" alt="زيت سينا جولد 1 لتر"
              class="w-full h-full object-cover img-zoom" style="transition:transform 0.7s ease;" />
            <div style="position:absolute;inset:0;background:linear-gradient(to top, #d1ab4e 0%, rgba(209,171,78,0.15) 55%, transparent 100%);"></div>
            <div style="position:absolute;bottom:14px;right:16px;">
              <span style="background:rgba(255,255,255,0.9);backdrop-filter:blur(8px);border:1px solid rgba(255,255,255,0.4);color:#a3802e;font-weight:900;font-size:0.9rem;padding:0.3rem 0.9rem;border-radius:9999px;box-shadow:0 4px 10px rgba(0,0,0,0.05);">1 لتر</span>
            </div>
            <div style="position:absolute;top:25px;left:12px;">
              <span style="
                background:linear-gradient(135deg,rgba(224,85,53,0.92),rgba(185,50,30,0.92));
                backdrop-filter:blur(6px);color:#fff;font-weight:900;font-size:0.72rem;
                padding:0.25rem 0.7rem;border-radius:9999px;
                box-shadow:0 0 12px rgba(224,85,53,0.5);
              ">⚡ خصم 15% اليوم فقط</span>
            </div>
          </div>

          <div class="p-6 flex flex-col flex-grow">
            <h3 style="font-size:1.15rem;font-weight:900;color:#1a2614;margin-bottom:6px;line-height:1.3;">
              زيت زيتون بكر ممتاز من سيناء
            </h3>
            <p style="font-size:0.82rem;color:#3e4f35;margin-bottom:16px;line-height:1.6;font-weight:600;">
              معصور بكرة على البارد · حموضة أقل من 0.8% · يكفي العيلة شهر كامل
            </p>

            <!-- <ul class="space-y-2 mb-5 flex-grow">
              <li v-for="f in features[1]" :key="f" style="font-size:0.82rem;color:#1a2614;font-weight:700;display:flex;align-items:center;gap:0.5rem;">
                <span style="color:#ffffff;background:#1a2614;border-radius:50%;width:18px;height:18px;display:flex;align-items:center;justify-content:center;font-size:0.65rem;flex-shrink:0;">✓</span>{{ f }}
              </li>
            </ul> -->

            <div class="mb-5 p-4 rounded-xl" style="background:rgba(255,255,255,0.5);border:1px solid rgba(255,255,255,0.8);">
              <div style="font-size:0.7rem;color:#3e4f35;font-weight:800;margin-bottom:4px;letter-spacing:0.05em;">السعر بعد خصم اليوم</div>
              <div style="display:flex;align-items:flex-end;gap:10px;flex-wrap:wrap;">
                <span style="font-size:2.8rem;font-weight:900;color:#1a2614;line-height:1;">580</span>
                <div style="padding-bottom:6px;">
                  <div style="font-size:1rem;color:#1a2614;font-weight:800;line-height:1;">جنيه</div>
                  <div style="font-size:0.8rem;text-decoration:line-through;color:#b9321e;line-height:1.4;">640</div>
                </div>
              </div>
              <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:10px;">
                <span style="background:rgba(255,255,255,0.9);border:1px solid #fff;color:#1a2614;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">💰 وفرت 60 جنيه</span>
                <span style="background:rgba(224,85,53,0.15);border:1px solid rgba(224,85,53,0.3);color:#b9321e;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">⚡ اليوم فقط</span>
              </div>
            </div>

            <a href="#order" @click.prevent="order('1L','510')"
              class="block text-center py-4 rounded-xl"
              style="background:#1a2614;color:#ffffff;font-size:1rem;font-weight:800;transition:all 0.3s ease;box-shadow:0 10px 20px rgba(0,0,0,0.15);">
              🛒 اطلب الآن — التوصيل لحد بابك
            </a>
            <p style="text-align:center;font-size:0.7rem;color:#3e4f35;margin-top:0.5rem;font-weight:700;">الدفع عند الاستلام | توصيل خلال 48 ساعة</p>
          </div>
        </div>

        <div class="price-card gsap-fade-up flex flex-col overflow-hidden"
          style="background: linear-gradient(145deg, #dfbc62 0%, #d1ab4e 100%); border:1px solid rgba(255,255,255,0.6);border-radius:1.5rem;box-shadow:0 15px 35px rgba(214,181,92,0.2);transition:all 0.35s cubic-bezier(0.4,0,0.2,1);">

          <div style="height:3px;background:rgba(255,255,255,0.5);"></div>

          <div class="relative overflow-hidden" style="height:240px;">
            <img src="/assets_v1/poster4.png" alt="زيت سينا جولد 3 لتر"
              class="w-full h-full object-cover img-zoom" style="transition:transform 0.7s ease;" />
            <div style="position:absolute;inset:0;background:linear-gradient(to top, #d1ab4e 0%, rgba(209,171,78,0.1) 50%, transparent 100%);"></div>
            <div style="position:absolute;bottom:14px;right:16px;">
              <span style="background:rgba(255,255,255,0.9);backdrop-filter:blur(8px);border:1px solid rgba(255,255,255,0.4);color:#a3802e;font-weight:900;font-size:0.85rem;padding:0.3rem 0.8rem;border-radius:9999px;box-shadow:0 4px 10px rgba(0,0,0,0.05);">3 لتر</span>
            </div>
            <div style="position:absolute;top:12px;left:12px;">
              <span style="background:rgba(26,38,20,0.85);backdrop-filter:blur(6px);color:#fff;font-weight:700;font-size:0.72rem;padding:0.25rem 0.7rem;border-radius:9999px;border:1px solid rgba(255,255,255,0.2);">🏠 خيار العيلة</span>
            </div>
            <div style="position:absolute;top:12px;right:12px;">
              <span style="
                background:linear-gradient(135deg,rgba(224,85,53,0.9),rgba(185,50,30,0.9));
                backdrop-filter:blur(6px);color:#fff;font-weight:900;font-size:0.7rem;
                padding:0.25rem 0.65rem;border-radius:9999px;
                box-shadow:0 0 10px rgba(224,85,53,0.4);
              ">خصم 15%</span>
            </div>
          </div>

          <div class="p-6 flex flex-col flex-grow">
            <h3 style="font-size:1.05rem;font-weight:900;color:#1a2614;margin-bottom:6px;line-height:1.3;">
              طقم زيت سيناء الفاخر
            </h3>
            <p style="font-size:0.8rem;color:#3e4f35;margin-bottom:16px;line-height:1.6;font-weight:600;">
              معصور بكرة على البارد · هدية مثالية أو للعيلة الكبيرة
            </p>

            <!-- <ul class="space-y-1.5 mb-5 flex-grow">
              <li v-for="f in features[2]" :key="f" style="font-size:0.8rem;color:#1a2614;font-weight:700;display:flex;align-items:center;gap:0.5rem;">
                <span style="color:#ffffff;background:#1a2614;border-radius:50%;width:16px;height:16px;display:flex;align-items:center;justify-content:center;font-size:0.6rem;flex-shrink:0;">✓</span>{{ f }}
              </li>
            </ul> -->

            <div class="mb-5 p-4 rounded-xl" style="background:rgba(255,255,255,0.4);border:1px solid rgba(255,255,255,0.7);">
              <div style="font-size:0.7rem;color:#3e4f35;font-weight:800;margin-bottom:4px;letter-spacing:0.05em;">السعر بعد خصم اليوم</div>
              <div style="display:flex;align-items:flex-end;gap:10px;flex-wrap:wrap;">
                <span style="font-size:2.4rem;font-weight:900;color:#1a2614;line-height:1;">1700</span>
                <div style="padding-bottom:5px;">
                  <div style="font-size:0.95rem;color:#1a2614;font-weight:800;line-height:1;">جنيه</div>
                  <div style="font-size:1.5rem;font-weight:600;font-weight:600;text-decoration:line-through;color:#b9321e;line-height:1.4;">1920</div>
                </div>
              </div>
              <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:10px;">
                <span style="background:rgba(255,255,255,0.8);border:1px solid rgba(255,255,255,1);color:#1a2614;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">💰 وفرت 120 جنيه</span>
                <span style="background:rgba(224,85,53,0.15);border:1px solid rgba(224,85,53,0.3);color:#b9321e;font-size:0.72rem;font-weight:800;padding:0.2rem 0.65rem;border-radius:9999px;">⚡ اليوم فقط</span>
              </div>
            </div>

            <a href="#order" @click.prevent="order('3L','1700')"
              class="cta-secondary block text-center py-3.5 rounded-xl font-bold"
              style="font-size:0.95rem;">
              اطلب الطقم الآن →
            </a>
          </div>
        </div>

      </div><div class="mt-10 value-strip gsap-fade-up">
        <div class="glass-card p-6 md:p-8" style="background: rgba(245, 245, 245, 0.7); border: 1px solid rgba(0,0,0,0.05); border-radius: 1.5rem;">
          <div class="grid grid-cols-1 sm:grid-cols-3 gap-6 text-center">
            <div v-for="v in valueProps" :key="v.title" class="flex flex-col items-center gap-2">
              <div style="font-size:2rem;">{{ v.icon }}</div>
              <h4 style="font-weight:800;color:#1a2614;font-size:1rem;">{{ v.title }}</h4>
              <p style="font-size:0.85rem;color:#4a5568;line-height:1.5;">{{ v.desc }}</p>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-8 text-center final-cta gsap-fade-up">
        <p style="color:#ef4444;font-weight:700;font-size:0.85rem;margin-bottom:1rem;">
          ⚡ خصم 15% اليوم فقط — العرض ينتهي عند منتصف الليل
        </p>
        <a href="#order" @click.prevent="scrollTo('order')" class="text-lg px-10 py-4 rounded-full" style="display: inline-block; background: #d6b55c; color: #fff; font-weight: 900; box-shadow: 0 10px 25px rgba(214,181,92,0.4); text-shadow: 0 1px 2px rgba(0,0,0,0.1); border: 1px solid rgba(255,255,255,0.3);">
          🛒 اطلب الآن — الدفع عند الاستلام
        </a>
        <div style="display:flex;align-items:center;justify-content:center;gap:1.5rem;margin-top:1rem;flex-wrap:wrap;">
          <span v-for="g in guarantees" :key="g" style="font-size:0.8rem;color:#2c4820;font-weight:700;display:flex;align-items:center;gap:0.25rem;">{{ g }}</span>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

/* ── Helpers ── */
const scrollTo = (id) => document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });

const order = (size, price) => {
  scrollTo('order');
  window.dispatchEvent(new CustomEvent('select-product', { detail: { size, price } }));
};

const pad = (n) => String(n).padStart(2, '0');

/* ── Countdown Timer (resets to midnight each night) ── */
const getTimeUntilMidnight = () => {
  const now  = new Date();
  const end  = new Date();
  end.setHours(23, 59, 59, 999);
  const diff = Math.max(0, end - now);
  return {
    hours:   Math.floor(diff / 3_600_000),
    minutes: Math.floor((diff % 3_600_000) / 60_000),
    seconds: Math.floor((diff % 60_000)    / 1_000),
  };
};

const timer    = ref(getTimeUntilMidnight());
let timerInterval = null;

/* ── Static data ── */
const features = [
  ['زيت بكر ممتاز من مزارع سيناء', 'معصور بكرة على البارد', 'حموضة أقل من 0.8%', 'مثالي للتجربة والتذوق'],
  ['زيت بكر ممتاز من مزارع سيناء', 'معصور بكرة على البارد', 'حموضة أقل من 0.8%', 'يكفي العيلة شهر كامل', 'توفير 60 جنيه عن السعر العادي'],
  ['زيت بكر ممتاز من مزارع سيناء', 'معصور بكرة على البارد', 'حموضة أقل من 0.8%', 'توفير 220 جنيه من السعر الأصلي', 'مثالي للهدايا والعيلة الكبيرة'],
];

const valueProps = [
  { icon: '🌿', title: 'طبيعي 100% من سيناء',      desc: 'لا إضافات كيميائية — مباشر من المزرعة لمائدتك' },
  { icon: '🏆', title: 'أفضل سعر مضمون',            desc: 'لو لقيت أرخص بنفس الجودة هنرد عليك الفرق' },
  { icon: '🚚', title: 'توصيل 48 ساعة لكل مصر',      desc: 'الدفع عند الاستلام — مش محتاج تدفع قبل ما تشوف المنتج' },
];

const guarantees = ['✓ دفع عند الاستلام', '✓ ضمان الجودة', '✓ توصيل لكل المحافظات'];

/* ── Lifecycle ── */
onMounted(() => {
  timerInterval = setInterval(() => { timer.value = getTimeUntilMidnight(); }, 1000);

  gsap.to('.section-hdr', { scrollTrigger: { trigger: '.section-hdr', start: 'top 85%' }, y: 0, opacity: 1, duration: 0.8, ease: 'power3.out' });
  gsap.to('.scarcity-strip', { scrollTrigger: { trigger: '.scarcity-strip', start: 'top 88%' }, y: 0, opacity: 1, duration: 0.6, delay: 0.15, ease: 'power2.out' });
  gsap.to('.discount-banner', { scrollTrigger: { trigger: '.discount-banner', start: 'top 88%' }, y: 0, opacity: 1, duration: 0.75, delay: 0.1, ease: 'power3.out' });
  gsap.to('.price-card', { scrollTrigger: { trigger: '.price-card', start: 'top 85%' }, y: 0, opacity: 1, duration: 0.7, stagger: 0.15, ease: 'power3.out' });
  gsap.to('.value-strip', { scrollTrigger: { trigger: '.value-strip', start: 'top 90%' }, y: 0, opacity: 1, duration: 0.7, ease: 'power3.out' });
  gsap.to('.final-cta', { scrollTrigger: { trigger: '.final-cta', start: 'top 92%' }, y: 0, opacity: 1, duration: 0.7, ease: 'power3.out' });

  document.querySelectorAll('.price-card').forEach(card => {
    const img = card.querySelector('.img-zoom');
    if (!img) return;
    card.addEventListener('mouseenter', () => gsap.to(img, { scale: 1.07, duration: 0.6, ease: 'power2.out' }));
    card.addEventListener('mouseleave', () => gsap.to(img, { scale: 1,    duration: 0.6, ease: 'power2.out' }));
  });
});

onUnmounted(() => { clearInterval(timerInterval); });
</script>

<style scoped>
/* ── Discount Banner ── */
.discount-banner { opacity: 0; transform: translateY(18px); }

.banner-glow-border {
  position: absolute; inset: 0; border-radius: 1.25rem;
  background: linear-gradient(135deg, #d6b55c 0%, #e05535 25%, #d6b55c 50%, #e05535 75%, #d6b55c 100%);
  background-size: 300% 300%; animation: borderShift 4s linear infinite; filter: blur(1px);
}
@keyframes borderShift { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }

.timer-block {
  display: flex; flex-direction: column; align-items: center; background: rgba(214,181,92,0.07); border: 1px solid rgba(214,181,92,0.2); border-radius: 0.65rem; padding: 0.45rem 0.85rem; min-width: 58px;
}
.timer-block--sec { background: rgba(224,85,53,0.08); border-color: rgba(224,85,53,0.25); }

.timer-digit {
  font-size: 1.9rem; font-weight: 900; line-height: 1; background: linear-gradient(135deg, #d6b55c, #eec765); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-variant-numeric: tabular-nums; letter-spacing: 0.02em;
}
.timer-block--sec .timer-digit { background: linear-gradient(135deg, #ff7755, #ffaa88); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }

.timer-label { font-size: 0.64rem; color: #a3802e; font-weight: 700; margin-top: 2px; letter-spacing: 0.04em; }
.timer-colon { font-size: 2rem; font-weight: 900; color: rgba(214,181,92,0.35); line-height: 1; padding-bottom: 18px; }

/* ── Standard card hover (Adjusted for Soft Gold) ── */
.price-card:hover {
  border-color: #fff !important;
  box-shadow: 0 25px 50px rgba(214,181,92,0.3), 0 0 20px rgba(214,181,92,0.15) !important;
  transform: translateY(-7px) !important;
}

/* ── Hero card hover ── */
.hero-card { transform: scale(1.03); }
.hero-card:hover {
  transform: scale(1.05) translateY(-7px) !important;
  box-shadow: 0 30px 60px rgba(214,181,92,0.4), 0 0 30px rgba(214,181,92,0.2) !important;
  border-color: #fff !important;
}

/* ── Secondary CTA ── */
.cta-secondary {
  background: rgba(255, 255, 255, 0.7);
  border: 1.5px solid rgba(255, 255, 255, 1);
  color: #1a2614;
  font-family: 'Cairo', sans-serif;
  cursor: pointer;
  text-decoration: none;
  transition: all 0.25s ease;
}
.cta-secondary:hover {
  background: #1a2614;
  border-color: #1a2614;
  color: #fff;
  transform: translateY(-1px);
}

/* Mobile: reset hero card scale */
@media (max-width: 768px) {
  .hero-card { transform: scale(1) !important; }
  .hero-card:hover { transform: translateY(-5px) !important; }
  .timer-block { min-width: 50px; padding: 0.35rem 0.6rem; }
  .timer-digit { font-size: 1.55rem; }
}
</style>