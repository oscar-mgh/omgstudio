<script setup>
const ventajas = [
  {
    title: 'Velocidad de carga superior',
    description: 'Cero código basura o plugins innecesarios. Tu sitio carga en milisegundos, mejorando la retención de usuarios.',
  },
  {
    title: 'Diseño 100% exclusivo',
    description: 'Sin plantillas prefabricadas. La interfaz se construye desde cero alineada a la identidad única de tu marca.',
  },
  {
    title: 'Máxima seguridad y control',
    description: 'Menos exposición a vulnerabilidades de plugins desactualizados y cero sorpresas por costos de licencias de terceros.',
  },
  {
    title: 'Escalabilidad ilimitada',
    description: 'Preparado para crecer. Integra plataformas avanzadas, cotizadores o pasarelas de pago sin restricciones de un CMS.',
  },
];
</script>

<template>
  <section
    id="por-que-desarrollo-a-medida"
    class="bg-brand-950 px-9 pt-20 pb-12 lg:pt-28 lg:pb-16 text-white border-b border-brand-800">
    <div class="mx-auto max-w-[1150px]">
      <div class="max-w-[680px]">
        <p class="mb-[18px] font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">
          Código a medida vs. Plantillas tradicionales
        </p>
        <h2 class="mb-5 text-[clamp(2rem,3.7vw,3.8rem)] font-bold leading-tight tracking-[-.055em]">
          ¿Por qué elegir un <em class="font-sans not-italic font-extrabold text-brand-300">desarrollo personalizado?</em>
        </h2>
        <p class="text-base leading-[1.8] text-brand-300">
          Un sitio web construido a medida supera los límites de los maquetadores genéricos para ofrecer rendimiento, seguridad y resultados
          reales.
        </p>
      </div>

      <div class="mt-12 grid gap-6 sm:grid-cols-2 lg:grid-cols-4">
        <article
          v-for="(item, index) in ventajas"
          :key="index"
          class="flex flex-col border border-brand-600 bg-brand-700 p-6 shadow-[9px_9px_0_#080a1a] transition-transform hover:-translate-y-1">
          <span class="mb-4 font-mono text-xs font-bold text-brand-300"> 0{{ index + 1 }} </span>

          <h3 class="mb-3 text-lg font-bold leading-snug text-slate-100">
            {{ item.title }}
          </h3>

          <p class="text-sm leading-relaxed text-brand-300">
            {{ item.description }}
          </p>
        </article>
      </div>
      <div
        class="mt-10 flex flex-wrap items-center justify-between gap-4 border-l-2 border-brand-300 bg-brand-900/50 p-4 text-xs text-brand-300 font-mono">
        <p>⚡ Optimización SEO nativa y estructura adaptada a estándares modernos de Google.</p>
        <a
          href="#contacto"
          class="font-bold underline hover:text-white"
          >Consulta tu proyecto &rarr;</a
        >
      </div>
    </div>
  </section>
</template>
