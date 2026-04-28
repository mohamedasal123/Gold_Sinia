<template>
  <footer style="background: linear-gradient(180deg,#0d1509 0%,#070e05 100%); position:relative; overflow:hidden; padding-top:5rem; padding-bottom:2rem;">
    <div style="position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,#C9A84C,transparent);"></div>
    <div style="position:absolute;inset:0;opacity:0.018;pointer-events:none;background-image:radial-gradient(circle at 2px 2px,#C9A84C 1px,transparent 0);background-size:28px 28px;"></div>

    <div class="max-w-6xl mx-auto px-4 sm:px-6 relative z-10">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-12 pb-16" style="border-bottom:1px solid rgba(74,125,37,0.12);">

        <!-- Brand -->
        <div>
          <div class="flex items-center gap-3 mb-5">
            <div style="width:48px;height:48px;border-radius:50%;background:linear-gradient(135deg,#C9A84C,#a88935);display:flex;align-items:center;justify-content:center;color:#fff;font-size:1.1rem;font-weight:900;box-shadow:0 0 20px rgba(201,168,76,0.35);">سG</div>
            <div>
              <h2 style="font-size:1.4rem;font-weight:900;color:#eef5e8;line-height:1.2;">سينا جولد</h2>
              <p style="font-size:0.7rem;color:#5a9e32;font-weight:600;">Sina Gold Olive Oil</p>
            </div>
          </div>
          <p style="color:#567048;font-size:0.88rem;line-height:1.75;font-weight:500;margin-bottom:1.5rem;">
            زيت زيتون طبيعي 100% من مزارع سيناء الأصيلة. معصور بكرة على البارد بأيدي مزارعينا لصحة أفضل لك ولعائلتك.
          </p>
          <a href="https://wa.me/201551866195" target="_blank" rel="noopener"
            class="btn-wa inline-flex text-sm px-5 py-2.5">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12.031 6.172c-3.181 0-5.767 2.586-5.768 5.766-.001 1.298.38 2.27 1.019 3.287l-.582 2.128 2.182-.573c.978.58 1.911.928 3.145.929 3.178 0 5.767-2.587 5.768-5.766.001-3.187-2.575-5.77-5.764-5.771zm3.392 8.244c-.144.405-.837.774-1.17.824-.299.045-.677.063-1.092-.125-.339-.153-.889-.356-1.785-.886-1.139-.672-1.89-1.802-1.947-1.879-.057-.077-.464-.618-.464-1.178 0-.56.289-.838.391-.947.102-.109.222-.136.297-.136l.214.004c.068.004.156-.027.244.184l.328.792c.027.054.045.118.012.191-.034.073-.051.118-.102.219-.051.101-.107.219-.153.272-.051.063-.105.129-.044.234.061.105.274.453.586.733.404.362.748.475.857.531.109.056.173.045.237-.027.064-.073.277-.323.352-.434.075-.111.149-.092.245-.056l.713.339c.105.051.175.077.201.12.026.043.026.25-.118.655z"/>
            </svg>
            واتساب مباشر
          </a>
        </div>

        <!-- Nav -->
        <div>
          <h3 style="font-weight:700;color:#eef5e8;margin-bottom:1.25rem;font-size:0.95rem;">التنقل السريع</h3>
          <ul style="list-style:none;padding:0;margin:0;display:flex;flex-direction:column;gap:0.65rem;">
            <li v-for="l in links" :key="l.id">
              <a :href="'#'+l.id" @click.prevent="go(l.id)"
                style="color:#567048;font-size:0.88rem;font-weight:500;text-decoration:none;display:flex;align-items:center;gap:0.4rem;transition:color 0.2s;"
                class="hover:text-[#C9A84C]">
                <span style="color:rgba(201,168,76,0.4);">›</span> {{ l.label }}
              </a>
            </li>
          </ul>
        </div>

        <!-- Contact -->
        <div>
          <h3 style="font-weight:700;color:#eef5e8;margin-bottom:1.25rem;font-size:0.95rem;">تواصل معنا</h3>
          <div style="display:flex;flex-direction:column;gap:0.9rem;">
            <a href="https://wa.me/201551866195" target="_blank"
              style="color:#567048;font-size:0.88rem;font-weight:500;text-decoration:none;display:flex;align-items:center;gap:0.6rem;transition:color 0.2s;"
              class="hover:text-[#25D366]">
              <span style="font-size:1.1rem;">📱</span> 01551866195
            </a>
            <a href="mailto:mohamediibrahim785@gmail.com"
              style="color:#567048;font-size:0.88rem;font-weight:500;text-decoration:none;display:flex;align-items:center;gap:0.6rem;transition:color 0.2s;"
              class="hover:text-[#C9A84C]">
              <span style="font-size:1.1rem;">📧</span> mohamediibrahim785@gmail.com
            </a>
            <p style="color:#567048;font-size:0.88rem;font-weight:500;display:flex;align-items:flex-start;gap:0.6rem;">
              <span style="font-size:1.1rem;flex-shrink:0;">📍</span> مزارع شبه جزيرة سيناء، مصر
            </p>
            <p style="color:#567048;font-size:0.88rem;font-weight:500;display:flex;align-items:flex-start;gap:0.6rem;">
              <span style="font-size:1.1rem;flex-shrink:0;">🕒</span> توصيل خلال 48 ساعة لكل المحافظات
            </p>
          </div>

          <div class="mt-5 p-4 glass-card" style="border-radius:1rem;">
            <p style="color:#C9A84C;font-weight:700;font-size:0.82rem;margin-bottom:3px;">⚡ الكمية محدودة</p>
            <p style="color:#567048;font-size:0.76rem;">اطلب الآن لضمان حصتك من أفضل موسم زيتون</p>
          </div>
        </div>
      </div>

      <!-- Bottom -->
      <div class="flex flex-col sm:flex-row items-center justify-between gap-3 pt-6"
        style="font-size:0.76rem;color:#3a5030;">
        <p>&copy; {{ new Date().getFullYear() }} سينا جولد. جميع الحقوق محفوظة.</p>
        <p style="display:flex;align-items:center;gap:0.4rem;">صُنع بـ <span style="color:#ef4444;">❤️</span> في مصر</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
const go = (id) => document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
const links = [
  { id:'hero',     label:'الرئيسية' },
  { id:'benefits', label:'الفوائد الصحية' },
  { id:'why-us',   label:'قصتنا' },
  { id:'products', label:'المنتجات' },
  // { id:'reviews',  label:'آراء العملاء' },
  { id:'order',    label:'اطلب الآن' },
];
</script>
