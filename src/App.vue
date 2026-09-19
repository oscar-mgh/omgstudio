<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue';
import AdventagesSection from './components/AdventagesSection.vue';
import ContactSection from './components/ContactSection.vue';
import ExtrasSection from './components/ExtrasSection.vue';
import HeroSection from './components/HeroSection.vue';
import PlansSection from './components/PlansSection.vue';
import ProcessSection from './components/ProcessSection.vue';

const menuOpen = ref(false);
const scrolled = ref(false);
function goTo(id) {
  menuOpen.value = false;
  document.querySelector(id)?.scrollIntoView({ behavior: 'smooth' });
}

function updateScroll() {
  scrolled.value = window.scrollY > 16;
}

onMounted(() => {
  window.addEventListener('scroll', updateScroll, { passive: true });
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', updateScroll);
});
</script>

<template>
  <main class="min-h-screen overflow-x-hidden bg-brand-950 text-slate-100 antialiased select-none">
    <header
      class="fixed inset-x-0 top-0 z-40 flex h-16.25 items-center justify-between px-9 pt-4 lg:pt-0 transition-colors lg:px-[max(28px,calc((100%-1150px)/2))]"
      :class="{ 'bg-brand-950/95 shadow-[0_1px_0_rgba(129,140,248,.15)] backdrop-blur-xl': scrolled }">
      <a
        class="flex items-center gap-2 text-[1.05rem] font-extrabold tracking-[-.06em]"
        href="#inicio">
        <svg
          class="h-9 w-9 text-brand-500"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          aria-label="OMG Studio Logo">
          <rect
            x="2"
            y="2"
            width="20"
            height="20"
            rx="5"
            fill="currentColor" />

          <path
            d="M7.5 9.5L10.5 12L7.5 14.5"
            stroke="white"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round" />

          <rect
            x="12.5"
            y="13.5"
            width="4.5"
            height="1.8"
            rx="0.9"
            fill="white" />
        </svg>

        <span> OMG Studio </span>
      </a>

      <button
        class="relative z-50 flex h-11 w-11 flex-col items-center justify-center gap-[5px] rounded border border-brand-600 bg-brand-700 lg:hidden"
        type="button"
        :aria-expanded="menuOpen"
        :aria-label="menuOpen ? 'Cerrar menú' : 'Abrir menú'"
        @click="menuOpen = !menuOpen">
        <span
          class="h-0.5 w-5 rounded-full bg-slate-100 transition-transform"
          :class="{ 'translate-y-[7px] rotate-45': menuOpen }"></span
        ><span
          class="h-0.5 w-5 rounded-full bg-slate-100 transition-opacity"
          :class="{ 'opacity-0': menuOpen }"></span
        ><span
          class="h-0.5 w-5 rounded-full bg-slate-100 transition-transform"
          :class="{ '-translate-y-[7px] -rotate-45': menuOpen }"></span>
      </button>

      <nav
        class="fixed inset-y-0 right-0 z-40 flex h-dvh w-[min(360px,86vw)] translate-x-full flex-col gap-2 overflow-y-auto border-l border-brand-600 bg-brand-900 px-7 pb-8 pt-[104px] shadow-[-18px_0_44px_rgba(3,5,20,.32)] transition-transform lg:static lg:z-auto lg:flex lg:h-auto lg:w-auto lg:translate-x-0 lg:flex-row lg:items-center lg:gap-7 lg:overflow-visible lg:border-0 lg:bg-transparent lg:p-0 lg:shadow-none"
        :class="{ '!translate-x-0': menuOpen }"
        aria-label="Navegación principal">
        <a
          class="flex min-h-[52px] items-center px-1 text-base font-bold text-slate-100/75 hover:text-slate-100 lg:min-h-0 lg:text-xs"
          href="#planes"
          @click.prevent="goTo('#planes')"
          >Planes</a
        >
        <a
          class="flex min-h-[52px] items-center px-1 text-base font-bold text-slate-100/75 hover:text-slate-100 lg:min-h-0 lg:text-xs"
          href="#adicionales"
          @click.prevent="goTo('#adicionales')"
          >Extras</a
        >
        <a
          class="flex min-h-[52px] items-center px-1 text-base font-bold text-slate-100/75 hover:text-slate-100 lg:min-h-0 lg:text-xs"
          href="#proceso"
          @click.prevent="goTo('#proceso')"
          >Proceso</a
        >
        <a
          class="flex min-h-[52px] items-center px-1 text-base font-bold text-slate-100/75 hover:text-slate-100 lg:min-h-0 lg:text-xs"
          href="#contacto"
          @click.prevent="goTo('#contacto')"
          >Contacto</a
        >
      </nav>
    </header>
    <button
      v-if="menuOpen"
      class="fixed inset-0 z-30 bg-brand-950/60 backdrop-blur-[2px] lg:hidden"
      type="button"
      aria-label="Cerrar menú"
      @click="menuOpen = false"></button>

    <HeroSection
      @contact="goTo('#contacto')"
      @plans="goTo('#planes')" />
    <AdventagesSection />
    <PlansSection />
    <ExtrasSection />
    <ProcessSection />
    <ContactSection />
  </main>
</template>
