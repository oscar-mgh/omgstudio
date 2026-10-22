<script setup>
const plans = [
  {
    name: 'Landing Page',
    audience: 'Para comenzar',
    text: 'Perfecta para promocionar un negocio, servicio o marca personal.',
    featured: false,
    features: [
      'Diseño responsive (adaptable a móviles y tablets)',
      'Modo claro / oscuro personalizado y paleta de colores',
      'Portada e información principal',
      'Botón de WhatsApp o formulario de contacto',
      'SEO básico, hosting y SSL',
      'Configuración y publicación',
    ],
  },
  {
    name: 'Sitio Web Profesional',
    audience: 'Para crecer',
    text: 'Para empresas y proyectos que necesitan mostrar más y crecer.',
    featured: true,
    features: [
      'Todo lo del plan Landing',
      'Múltiples páginas',
      'Catálogo de productos o servicios',
      'Formularios personalizados',
      'Conecta con redes sociales o algun CRM (hubspot, zoho, etc)',
      'Preparada para escalar a tienda online o plataforma avanzada',
    ],
  },
];
</script>

<template>
  <section
    id="planes"
    class="bg-brand-950 px-9 pt-20 pb-8 lg:py-26 border-b border-brand-800">
    <div class="mx-auto max-w-[1150px]">
      <div class="reveal mx-auto max-w-[570px] text-center sm:mx-0 sm:text-left">
        <p class="mb-[18px] font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">
          Planes estrategicos para resultados extraordinarios
        </p>
        <h2 class="mb-5 max-w-[760px] text-[clamp(2rem,3.7vw,3.8rem)] font-bold leading-tight tracking-[-.055em]">
          Elige el punto de partida <em class="font-sans not-italic font-extrabold text-brand-300">ideal para ti.</em>
        </h2>
        <p class="text-base leading-[1.8] text-brand-300">
          Soluciones digitales diseñadas para comunicar, conectar y organizar tu negocio.
        </p>
      </div>
      <div class="mt-12 grid gap-6 lg:grid-cols-2">
        <article
          v-for="plan in plans"
          :key="plan.name"
          class="reveal relative flex min-h-0 flex-col rounded border border-brand-600 bg-brand-700 p-6 transition duration-200 ease-out hover:-translate-y-1 hover:shadow-[0_16px_35px_rgba(3,5,20,.28)] lg:min-h-[580px] lg:p-9"
          :class="plan.featured ? 'border-2 border-brand-300' : ''">
          <p
            v-if="plan.featured"
            class="absolute -top-3 right-6 rounded bg-brand-300 px-3 py-2 font-mono text-[10px] uppercase tracking-wider text-brand-950">
            Recomendado
          </p>
          <p class="font-mono text-[11px] uppercase tracking-wider text-brand-300">{{ plan.name }}</p>
          <p class="my-3 text-[clamp(1.35rem,2vw,1.7rem)] font-extrabold tracking-tight text-brand-300">{{ plan.audience }}</p>
          <p class="min-h-0 text-sm leading-relaxed text-brand-300 lg:min-h-12">{{ plan.text }}</p>
          <div class="my-6 h-px bg-brand-600"></div>
          <p class="font-mono text-[11px] uppercase tracking-wider text-brand-300">Incluye</p>
          <ul class="my-5 mb-8 grid gap-3 text-sm">
            <li
              v-for="feature in plan.features"
              :key="feature"
              class="flex items-start gap-2">
              <span class="font-extrabold text-brand-300">✓</span>{{ feature }}
            </li>
          </ul>
        </article>
      </div>
    </div>
  </section>
</template>
