<template>
  <header ref="navbarEl" class="fixed top-0 left-0 right-0 z-50 transition-all duration-500"
    :class="scrolled ? 'navbar-scrolled' : 'navbar-top'">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 md:h-20">

        <!-- Logo -->
        <a href="#hero" @click.prevent="scrollTo('hero')" class="flex items-center gap-3 group flex-shrink-0">
        <div class="w-14 h-14 rounded-full overflow-hidden flex items-center justify-center shadow-[0_4px_14px_rgba(201,168,76,0.30)] group-hover:shadow-[0_6px_20px_rgba(201,168,76,0.45)] transition-all duration-300">
  <img src="/assets_v1/logo.png" alt="Logo" class="w-18 h-18 object-cover" />
</div>
          <div class="hidden sm:block">
            <span
              class="font-black text-xl text-[#0F1A0A] group-hover:text-[#C9A84C] transition-colors leading-tight tracking-tight">جولد
              سيناء</span>
            <p class="text-[10px] font-semibold text-[#3D7A1E] leading-tight">زيت زيتون سيناء</p>
          </div>
        </a>

        <!-- Desktop Nav -->
        <nav class="hidden lg:flex items-center gap-1">
          <a v-for="link in navLinks" :key="link.id" :href="'#' + link.id" @click.prevent="scrollTo(link.id)"
            class="nav-link px-4 py-2 rounded-full text-sm font-bold text-[#6B7E64] hover:text-[#0F1A0A] hover:bg-[#F2F4F6] transition-all duration-200">{{
              link.label }}</a>
        </nav>

        <!-- Right actions -->
        <div class="flex items-center gap-3">
          <a href="#order" @click.prevent="scrollTo('order')" class="btn-gold text-sm px-5 py-2.5 rounded-full">
            🛒 اطلب الآن
          </a>
          <button @click="mobileOpen = !mobileOpen"
            class="lg:hidden w-9 h-9 flex flex-col items-center justify-center gap-1.5" aria-label="قائمة">
            <span class="block w-5 h-0.5 bg-[#C9A84C] rounded transition-all duration-300"
              :class="mobileOpen ? 'rotate-45 translate-y-2' : ''"></span>
            <span class="block w-5 h-0.5 bg-[#C9A84C] rounded transition-all duration-300"
              :class="mobileOpen ? 'opacity-0' : ''"></span>
            <span class="block w-5 h-0.5 bg-[#C9A84C] rounded transition-all duration-300"
              :class="mobileOpen ? '-rotate-45 -translate-y-2' : ''"></span>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition name="mobile-menu">
      <div v-if="mobileOpen" class="lg:hidden bg-white/97 backdrop-blur-xl border-t border-black/[0.07]">
        <div class="max-w-7xl mx-auto px-4 py-4 flex flex-col gap-1">
          <a v-for="link in navLinks" :key="link.id" :href="'#' + link.id"
            @click.prevent="scrollTo(link.id); mobileOpen = false"
            class="flex items-center gap-3 px-4 py-3 rounded-xl text-[#6B7E64] font-bold hover:bg-[#F8F9FA] hover:text-[#C9A84C] transition-colors">
            <span>{{ link.icon }}</span><span>{{ link.label }}</span>
          </a>
          <div class="pt-3 border-t border-black/[0.07]">
            <a href="#order" @click.prevent="scrollTo('order'); mobileOpen = false"
              class="btn-gold w-full text-center py-3.5 block">
              🛒 اطلب الآن — التوصيل لحد بابك
            </a>
          </div>
        </div>
      </div>
    </Transition>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
defineProps({ isDark: Boolean });
defineEmits(['toggle-dark']);

const scrolled = ref(false);
const mobileOpen = ref(false);
const navLinks = [
  { id: 'hero', label: 'الرئيسية', icon: '🏠' },
  { id: 'benefits', label: 'الفوائد', icon: '✨' },
  { id: 'why-us', label: 'لماذا نحن', icon: '🫒' },
  { id: 'products', label: 'المنتجات', icon: '🛍️' },
  // { id: 'reviews',  label: 'آراء العملاء', icon: '⭐' },
  { id: 'order', label: 'اطلب الآن', icon: '📦' },
];
const scrollTo = (id) => document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
const onScroll = () => { scrolled.value = window.scrollY > 60; };
onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }));
onUnmounted(() => window.removeEventListener('scroll', onScroll));
</script>

<style scoped>
.navbar-top {
  background: transparent;
}

.navbar-scrolled {
  background: rgba(255, 255, 255, 0.94);
  backdrop-filter: blur(24px) saturate(1.6);
  -webkit-backdrop-filter: blur(24px) saturate(1.6);
  border-bottom: 1px solid rgba(0, 0, 0, 0.07);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.06), 0 0 0 0.5px rgba(0, 0, 0, 0.04);
}

.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: all 0.3s ease;
  overflow: hidden;
}

.mobile-menu-enter-from,
.mobile-menu-leave-to {
  max-height: 0;
  opacity: 0;
}

.mobile-menu-enter-to,
.mobile-menu-leave-from {
  max-height: 400px;
  opacity: 1;
}
</style>
