<script setup>
defineEmits(['contact', 'plans']);
</script>

<template>
  <section
    id="inicio"
    class="relative isolate min-h-[720px] bg-brand-800 px-6 pb-20 pt-40 lg:flex lg:items-center lg:px-0 lg:pb-0">
    <div class="mx-auto w-full max-w-[760px] lg:mx-0 lg:ml-[max(24px,calc((100%_-_1150px)_/_2))] lg:w-[calc(50%_-_26px)]">
      <p class="mb-[18px] font-bold text-[11px] uppercase tracking-[.09em] text-brand-300">
        <span class="mr-2 inline-block h-2 w-2 rounded-full bg-brand-400"></span>Diseño y desarrollo web personalizado
      </p>
      <h1 class="mb-6 max-w-[670px] text-[clamp(2.35rem,5.2vw,5.25rem)] font-bold leading-[1.05] tracking-[-.055em]">
        Tu negocio merece una web que <em class="font-sans not-italic font-extrabold text-brand-300">genere resultados.</em>
      </h1>
      <p class="max-w-[530px] text-[1.08rem] leading-[1.75] text-brand-300">
        Convierte visitas en clientes con un sitio rápido, atractivo y hecho a la medida de lo que tu negocio necesita.
      </p>
      <div class="mt-8 flex flex-wrap items-center gap-5 lg:gap-7">
        <button
          class="inline-flex min-h-[51px] items-center justify-center gap-4 bg-brand-300 px-[21px] text-sm font-bold text-brand-950 transition-transform rounded cursor-pointer hover:-translate-y-1"
          @click="$emit('contact')">
          Quiero mi sitio web
        </button>
        <button
          class="inline-flex min-h-[51px] items-center gap-4 bg-transparent px-0 text-sm font-bold text-slate-100 rounded cursor-pointer transition-transform hover:-translate-y-1"
          @click="$emit('plans')">
          Ver planes <span class="text-xl">↓</span>
        </button>
      </div>
      <div class="pb-6 mt-12 grid grid-cols-3 gap-4 lg:mt-18.75 lg:gap-8 text-center max-w-xl">
        <div class="grid gap-1">
          <strong class="text-xs">100%</strong>
          <span class="text-[11px] text-brand-300">Hecho a medida</span>
        </div>
        <div class="grid gap-1">
          <strong class="text-xs">SEO</strong>
          <span class="text-[11px] text-brand-300">Posiciona tu sitio en las busquedas</span>
        </div>
        <div class="grid gap-1">
          <strong class="text-xs">HTTPS</strong>
          <span class="text-[11px] text-brand-300">seguro y confiable</span>
        </div>
      </div>
    </div>
    <div
      class="relative mx-auto mt-12 h-[clamp(250px,42vw,455px)] w-[min(100%-32px,610px)] lg:absolute lg:right-[clamp(15px,5vw,100px)] lg:top-[153px] lg:mt-0"
      aria-hidden="true">
      <div
        class="absolute right-0 top-6 h-[calc(100%-26px)] w-[93%] rotate-2 overflow-hidden rounded-lg border-[7px] border-brand-500 bg-brand-800 rounded p-0 shadow-[0_35px_58px_rgba(3,5,20,.42)]">
        <div class="flex h-[42px] items-center gap-1 px-1">
          <i class="h-2 w-2 rounded-full bg-brand-400"></i><i class="h-2 w-2 rounded-full bg-brand-400"></i
          ><i class="h-2 w-2 rounded-full bg-brand-400"></i><span class="mx-auto h-[13px] w-[45%] rounded-full bg-brand-700"></span>
        </div>
        <div class="h-[calc(100%-42px)] bg-brand-900 p-[clamp(14px,3vw,30px)]">
          <div class="ml-auto h-2 w-[38%] bg-brand-400/70"></div>
          <div
            class="mt-[clamp(22px,5vw,52px)] h-[clamp(32px,6vw,48px)] w-[68%] bg-gradient-to-r from-slate-200 via-slate-200 to-transparent"></div>
          <div class="mt-3 h-2 w-[72%] bg-brand-400/70"></div>
          <div class="mt-3 h-2 w-[54%] bg-brand-400/70"></div>
          <div class="mt-6 h-7 w-[90px] bg-brand-500"></div>
          <div class="mt-8 flex gap-2">
            <b class="h-14 flex-1 bg-brand-800"></b><b class="h-14 flex-1 bg-brand-800"></b><b class="h-14 flex-1 bg-brand-800"></b>
          </div>
        </div>
      </div>
      <div class="absolute left-0 top-0 z-10 rotate-[-5deg] bg-brand-300 px-4 py-3 font-bold text-[13px] text-brand-950 rounded shadow-lg">
        + clientes
      </div>
      <div class="absolute bottom-0 right-0 z-10 rotate-[4deg] bg-brand-700 px-4 py-3 font-bold text-[13px] text-slate-100 rounded shadow-lg">
        ⚡ rápido
      </div>
    </div>
  </section>
</template>
