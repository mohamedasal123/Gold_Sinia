<template>
  <div>
    <!-- WhatsApp FAB -->
    <a href="https://wa.me/201551866195" target="_blank" rel="noopener"
      class="wa-pulse-anim fixed bottom-6 left-6 z-50 w-14 h-14 rounded-full flex items-center justify-center transition-transform duration-200 hover:scale-110"
      style="background:linear-gradient(135deg,#1a7a42,#25D366);"
      aria-label="واتساب">
      <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12.031 6.172c-3.181 0-5.767 2.586-5.768 5.766-.001 1.298.38 2.27 1.019 3.287l-.582 2.128 2.182-.573c.978.58 1.911.928 3.145.929 3.178 0 5.767-2.587 5.768-5.766.001-3.187-2.575-5.77-5.764-5.771zm3.392 8.244c-.144.405-.837.774-1.17.824-.299.045-.677.063-1.092-.125-.339-.153-.889-.356-1.785-.886-1.139-.672-1.89-1.802-1.947-1.879-.057-.077-.464-.618-.464-1.178 0-.56.289-.838.391-.947.102-.109.222-.136.297-.136l.214.004c.068.004.156-.027.244.184l.328.792c.027.054.045.118.012.191-.034.073-.051.118-.102.219-.051.101-.107.219-.153.272-.051.063-.105.129-.044.234.061.105.274.453.586.733.404.362.748.475.857.531.109.056.173.045.237-.027.064-.073.277-.323.352-.434.075-.111.149-.092.245-.056l.713.339c.105.051.175.077.201.12.026.043.026.25-.118.655z"/>
      </svg>
    </a>

    <!-- Sticky mobile CTA -->
    <Transition name="slide-up">
      <div v-if="showCta"
        class="fixed bottom-0 left-0 right-0 z-40 md:hidden px-4 pb-4 pt-2"
        style="background:linear-gradient(to top,rgba(13,21,9,0.95),transparent);">
        <a href="#order" @click.prevent="scrollTo('order')"
          class="btn-gold block w-full text-center py-4 text-lg rounded-2xl">
          🛒 اطلب الآن — الدفع عند الاستلام
        </a>
      </div>
    </Transition>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
const showCta = ref(true);
const scrollTo = (id) => document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
const onScroll = () => {
  const el = document.getElementById('order');
  if (!el) return;
  const r = el.getBoundingClientRect();
  showCta.value = !(r.top < window.innerHeight && r.bottom > 0);
};
onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }));
onUnmounted(() => window.removeEventListener('scroll', onScroll));
</script>

<style scoped>
.slide-up-enter-active, .slide-up-leave-active { transition: transform 0.3s ease, opacity 0.3s ease; }
.slide-up-enter-from, .slide-up-leave-to { transform: translateY(100%); opacity: 0; }
</style>
