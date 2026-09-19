<script setup>
const plans = [
  {
    name: 'Landing Page',
    audience: 'Para comenzar',
    text: 'Perfecta para promocionar un negocio, servicio o marca personal.',
    featured: false,
    features: [
      'Diseño responsive',
      'Tema claro - oscuro (paleta de colores personalizada)',
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
    class="bg-brand-950 px-6 pt-20 pb-8 lg:pt-26">
    <div class="mx-auto max-w-[1150px]">
      <div class="max-w-[570px]">
        <p class="mb-[18px] font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">Planes estrategicos para resultados extraordinarios</p>
        <h2 class="mb-5 max-w-[760px] text-[clamp(2rem,3.7vw,3.8rem)] font-bold leading-tight tracking-[-.055em]">
          Elige el punto de partida <em class="font-sans not-italic font-extrabold text-brand-300">ideal para ti.</em>
        </h2>
        <p class="text-base leading-[1.8] text-brand-300">
          Sin plantillas genéricas. Cada sitio se diseña para comunicar, conectar y convertir.
        </p>
      </div>
      <div class="mt-12 grid gap-6 lg:grid-cols-2">
        <article
          v-for="plan in plans"
          :key="plan.name"
          class="relative flex min-h-0 flex-col border border-brand-600 bg-brand-700 p-6 transition-transform hover:-translate-y-1 lg:min-h-[580px] lg:p-9"
          :class="plan.featured ? 'border-2 border-brand-300' : ''">
          <p
            v-if="plan.featured"
            class="absolute -top-3 right-6 bg-brand-300 px-3 py-2 font-mono text-[10px] uppercase tracking-wider text-brand-950">
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
          <a
            class="mt-auto inline-flex min-h-[51px] items-center justify-center gap-4 border border-brand-400 px-5 text-sm font-bold transition-colors hover:bg-brand-600"
            :class="plan.featured ? 'bg-brand-300 text-brand-950 hover:bg-slate-400' : 'text-zinc-300'"
            href="#contacto">
            Me interesa
          </a>
        </article>
      </div>
      <p class="mt-5 text-[12px] text-brand-300">
        Cada proyecto se define con alcance y objetivos claros. Escríbeme para conocer la mejor solución. <br>No se incluye diseño de logotipos, branding o ilustraciones personalizadas. <br> Se puede integrar logotipo existente e imagenes.
      </p>
    </div>
  </section>
</template>
