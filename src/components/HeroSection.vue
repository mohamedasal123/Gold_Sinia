<template>
  <!-- Hero keeps the video/cinematic look — overlays adjusted for refined whites -->
  <section id="hero" class="relative w-full h-screen min-h-[700px] flex items-center justify-center overflow-hidden">

    <!-- Video Background -->
    <video
      ref="videoEl"
      class="absolute inset-0 w-full h-full object-cover will-change-transform"
      autoplay
      muted
      loop
      playsinline
      preload="auto"
      poster="/assets_v1/poster1.png"
    >
      <source src="/assets_v1/download.mp4" type="video/mp4" />
    </video>

    <!-- Multi-layer overlay — lighter & more refined -->
    <div class="absolute inset-0 bg-gradient-to-t from-black/75 via-black/50 to-black/35 z-10"></div>
    <div class="absolute inset-0 bg-gradient-to-r from-black/50 via-transparent to-black/10 z-10"></div>
    <!-- Gold accent at bottom -->
    <div class="absolute bottom-0 left-0 right-0 h-px bg-gradient-to-r from-transparent via-[#C9A84C]/60 to-transparent z-20"></div>

    <!-- Hero Content -->
    <div class="relative z-20 w-full max-w-5xl mx-auto px-4 sm:px-6 text-center flex flex-col items-center">

      <!-- Pre-headline badge -->
      <div ref="badgeEl" class="gsap-fade-up mb-6">
        <span class="inline-flex items-center gap-2 bg-white/15 backdrop-blur-md border border-white/30 text-white font-bold px-5 py-2 rounded-full text-sm tracking-wider uppercase shadow-lg">
          🌿 من مزارع سيناء الأصيلة
        </span>
      </div>

      <!-- Main Headline -->
      <h1 ref="titleEl" class="gsap-fade-up text-white font-black leading-tight mb-6"
        style="font-size: clamp(2.2rem, 6vw, 5rem); text-shadow: 0 2px 20px rgba(0,0,0,0.3);">
        زيت زيتون طبيعي<br />
        <span class="text-gradient-gold">100% من قلب سيناء</span>
      </h1>

      <!-- Sub-headline -->
      <p ref="subEl" class="gsap-fade-up text-white/85 text-lg md:text-2xl mb-10 max-w-2xl leading-relaxed font-medium">
        بكر ممتاز معصور علي البارد · حموضة أقل من 0.8% · حصاد يدوي بأيدي مزارعينا
      </p>

      <!-- CTAs -->
      <div ref="ctaEl" class="gsap-fade-up flex flex-col sm:flex-row gap-4 items-center justify-center w-full">
        <a href="#order" @click.prevent="scrollTo('order')" class="btn-gold text-lg px-8 py-4 rounded-full w-full sm:w-auto">
          🛒 اطلب الآن — التوصيل لحد بابك
        </a>
        <a href="#benefits" @click.prevent="scrollTo('benefits')"
          class="inline-flex items-center gap-2 text-white border border-white/30 hover:border-white/55 backdrop-blur-sm bg-white/10 font-bold px-8 py-4 rounded-full transition-all duration-300 hover:bg-white/18 w-full sm:w-auto justify-center">
          اعرف أكتر ↓
        </a>
      </div>

      <!-- Urgency -->
      <div ref="urgencyEl" class="gsap-fade-up mt-6">
        <p class="inline-flex items-center gap-2 text-white/90 text-sm font-bold bg-red-600/65 backdrop-blur-sm px-5 py-2 rounded-full border border-red-500/35 shadow-lg">
          <span class="animate-pulse">⚡</span> الكمية محدودة جداً — لا تفوت الفرصة
        </p>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div ref="scrollIndicator" class="gsap-fade-in absolute bottom-8 left-1/2 -translate-x-1/2 z-20 flex flex-col items-center gap-2">
      <span class="text-white/45 text-xs font-medium tracking-widest uppercase">اسكرول للأسفل</span>
      <div class="w-6 h-10 border-2 border-white/25 rounded-full flex items-start justify-center pt-1.5">
        <div class="w-1.5 h-2.5 bg-[#C9A84C] rounded-full scroll-dot"></div>
      </div>
    </div>

    <!-- Social proof overlay -->
    <div ref="socialProofEl" class="gsap-fade-up absolute bottom-24 right-4 z-20 hidden md:block">
      <div class="bg-white/12 backdrop-blur-md border border-white/20 rounded-2xl p-4 shadow-xl max-w-[220px]">
        <div class="flex items-center gap-2 mb-2">
          <div class="flex -space-x-2 space-x-reverse">
            <div v-for="i in 3" :key="i" class="w-7 h-7 rounded-full bg-gradient-to-br from-[#C9A84C] to-[#3D7A1E] border-2 border-white flex items-center justify-center text-xs font-bold text-white">
              {{ ['أ','م','س'][i-1] }}
            </div>
          </div>
          <div class="flex text-[#C9A84C] text-sm">
            <span v-for="i in 5" :key="i">★</span>
          </div>
        </div>
        <p class="text-white text-xs font-semibold leading-relaxed"> العملاء سعداء بزيت سينا جولد</p>
      </div>
    </div>

  </section>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import gsap from 'gsap';

const videoEl = ref(null);
const badgeEl = ref(null);
const titleEl = ref(null);
const subEl = ref(null);
const ctaEl = ref(null);
const urgencyEl = ref(null);
const scrollIndicator = ref(null);
const socialProofEl = ref(null);

const scrollTo = (id) => {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
};

onMounted(() => {
  // Ken Burns on video
  gsap.fromTo(videoEl.value,
    { scale: 1 },
    { scale: 1.1, duration: 12, ease: 'sine.inOut', repeat: -1, yoyo: true }
  );

  // Staggered hero entrance
  const tl = gsap.timeline({ delay: 0.3 });

  tl.to(badgeEl.value, { y: 0, opacity: 1, duration: 0.7, ease: 'power3.out' })
    .to(titleEl.value, { y: 0, opacity: 1, duration: 0.8, ease: 'power3.out' }, '-=0.4')
    .to(subEl.value, { y: 0, opacity: 1, duration: 0.7, ease: 'power3.out' }, '-=0.5')
    .to(ctaEl.value, { y: 0, opacity: 1, duration: 0.7, ease: 'power3.out' }, '-=0.4')
    .to(urgencyEl.value, { y: 0, opacity: 1, duration: 0.5, ease: 'power3.out' }, '-=0.3')
    .to(scrollIndicator.value, { opacity: 1, duration: 0.6 }, '-=0.2')
    .to(socialProofEl.value, { y: 0, opacity: 1, duration: 0.6, ease: 'back.out(1.2)' }, '-=0.3');
});
</script>

<style scoped>
.text-gradient-gold {
  background: linear-gradient(135deg, #C9A84C, #e0c06a, #C9A84C);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.scroll-dot {
  animation: scroll-bounce 1.8s ease-in-out infinite;
}
@keyframes scroll-bounce {
  0%, 100% { transform: translateY(0); opacity: 1; }
  80%       { transform: translateY(14px); opacity: 0.3; }
}
</style>
