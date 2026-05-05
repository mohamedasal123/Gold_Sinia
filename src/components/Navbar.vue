<template>
  <header
    ref="navbarEl"
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-500"
    :class="scrolled ? 'navbar-scrolled' : 'navbar-top'"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 md:h-20">

        <!-- Logo -->
        <a href="#hero" @click.prevent="scrollTo('hero')" class="flex items-center gap-3 group flex-shrink-0">
          <div class="w-10 h-10 rounded-full bg-gradient-to-br from-[#C9A84C] to-[#a88935] flex items-center justify-center shadow-[0_0_15px_rgba(201,168,76,0.4)] group-hover:shadow-[0_0_25px_rgba(201,168,76,0.6)] transition-all duration-300">
            <span class="text-white font-black text-base leading-none">GS</span>
          </div>
          <div class="hidden sm:block">
            <span class="font-black text-xl text-[#eef5e8] group-hover:text-[#C9A84C] transition-colors leading-tight tracking-tight">جولد سيناء</span>
            <p class="text-[10px] font-semibold text-[#5a9e32] leading-tight">زيت زيتون سيناء</p>
          </div>
        </a>

        <!-- Desktop Nav -->
        <nav class="hidden lg:flex items-center gap-1">
          <a
            v-for="link in navLinks"
            :key="link.id"
            :href="'#' + link.id"
            @click.prevent="scrollTo(link.id)"
            class="nav-link px-4 py-2 rounded-full text-sm font-bold text-[#8aab78] hover:text-[#eef5e8] hover:bg-white/5 transition-all duration-200"
          >{{ link.label }}</a>
        </nav>

        <!-- Right actions -->
        <div class="flex items-center gap-3">
          <a href="#order" @click.prevent="scrollTo('order')" class="btn-gold text-sm px-5 py-2.5 rounded-full">
            🛒 اطلب الآن
          </a>
          <button
            @click="mobileOpen = !mobileOpen"
            class="lg:hidden w-9 h-9 flex flex-col items-center justify-center gap-1.5"
            aria-label="قائمة"
          >
            <span class="block w-5 h-0.5 bg-[#C9A84C] rounded transition-all duration-300" :class="mobileOpen ? 'rotate-45 translate-y-2' : ''"></span>
            <span class="block w-5 h-0.5 bg-[#C9A84C] rounded transition-all duration-300" :class="mobileOpen ? 'opacity-0' : ''"></span>
            <span class="block w-5 h-0.5 bg-[#C9A84C] rounded transition-all duration-300" :class="mobileOpen ? '-rotate-45 -translate-y-2' : ''"></span>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition name="mobile-menu">
      <div v-if="mobileOpen" class="lg:hidden bg-[#0d1509]/95 backdrop-blur-xl border-t border-[rgba(201,168,76,0.15)]">
        <div class="max-w-7xl mx-auto px-4 py-4 flex flex-col gap-1">
          <a
            v-for="link in navLinks"
            :key="link.id"
            :href="'#' + link.id"
            @click.prevent="scrollTo(link.id); mobileOpen = false"
            class="flex items-center gap-3 px-4 py-3 rounded-xl text-[#8aab78] font-bold hover:bg-white/5 hover:text-[#C9A84C] transition-colors"
          >
            <span>{{ link.icon }}</span><span>{{ link.label }}</span>
          </a>
          <div class="pt-3 border-t border-[rgba(201,168,76,0.12)]">
            <a href="#order" @click.prevent="scrollTo('order'); mobileOpen = false" class="btn-gold w-full text-center py-3.5 block">
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
  { id: 'hero',     label: 'الرئيسية',    icon: '🏠' },
  { id: 'benefits', label: 'الفوائد',      icon: '✨' },
  { id: 'why-us',   label: 'لماذا نحن',   icon: '🫒' },
  { id: 'products', label: 'المنتجات',     icon: '🛍️' },
  // { id: 'reviews',  label: 'آراء العملاء', icon: '⭐' },
  { id: 'order',    label: 'اطلب الآن',    icon: '📦' },
];
const scrollTo = (id) => document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
const onScroll = () => { scrolled.value = window.scrollY > 60; };
onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }));
onUnmounted(() => window.removeEventListener('scroll', onScroll));
</script>

<style scoped>
.navbar-top { background: transparent; }
.navbar-scrolled {
  background: rgba(13, 21, 9, 0.88);
  backdrop-filter: blur(24px) saturate(1.4);
  -webkit-backdrop-filter: blur(24px) saturate(1.4);
  border-bottom: 1px solid rgba(201,168,76,0.14);
  box-shadow: 0 4px 30px rgba(0,0,0,0.6), 0 0 0 0.5px rgba(201,168,76,0.1);
}
.mobile-menu-enter-active, .mobile-menu-leave-active { transition: all 0.3s ease; overflow: hidden; }
.mobile-menu-enter-from, .mobile-menu-leave-to { max-height: 0; opacity: 0; }
.mobile-menu-enter-to, .mobile-menu-leave-from { max-height: 400px; opacity: 1; }
</style>
