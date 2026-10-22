<script setup>
const steps = [
  ['01', 'Conocemos tu proyecto', 'Hablamos de tu negocio, objetivos, clientes y las funcionalidades que necesitas.'],
  [
    '02',
    'Definimos la estructura',
    'Organizamos el contenido y creamos hasta dos propuestas iniciales de wireframe para elegir la dirección del proyecto.',
  ],
  ['03', 'Diseñamos', 'Definimos la dirección visual y preparamos el diseño antes de comenzar el desarrollo.'],
  ['04', 'Desarrollamos', 'Convertimos la propuesta aprobada en un sitio rápido, responsive y funcional.'],
  ['05', 'Lanzamos', 'Configuramos el dominio, hosting y servicios necesarios para publicar tu proyecto.'],
];
</script>

<template>
  <section
    id="proceso"
    class="bg-brand-950 px-9 py-20 lg:py-28">
    <div class="mx-auto max-w-[1150px]">
      <div class="reveal mx-auto max-w-[760px] text-center">
        <p class="mb-[18px] font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">Simple y sin complicaciones</p>
        <h2 class="mb-5 text-[clamp(2rem,3.7vw,3.8rem)] font-bold leading-tight tracking-[-.055em]">
          De la idea a tu sitio <em class="font-sans not-italic font-extrabold text-brand-300">en cinco pasos.</em>
        </h2>
      </div>
      <div class="my-12 grid gap-8 sm:grid-cols-2 lg:my-16 lg:grid-cols-5">
        <article
          v-for="step in steps"
          :key="step[0]"
          class="reveal border-t border-brand-400 pt-4 transition duration-200 ease-out hover:-translate-y-1">
          <span class="font-mono text-xs text-brand-300">{{ step[0] }}</span>
          <h3 class="my-6 text-base font-bold">{{ step[1] }}</h3>
          <p class="text-sm leading-relaxed text-brand-300">{{ step[2] }}</p>
        </article>
      </div>
      <div class="reveal grid gap-6 rounded bg-brand-800 p-6 sm:grid-cols-[58px_1fr] sm:items-center lg:grid-cols-[70px_1fr_auto] lg:p-8">
        <div class="grid h-14 w-14 place-items-center rounded bg-brand-300 text-2xl text-brand-950">✦</div>
        <div>
          <p class="mb-1 font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">Tu proyecto es único</p>
          <h3 class="mb-2 text-lg font-bold">Todos los sitios son desarrollados a medida.</h3>
          <p class="text-sm leading-relaxed text-slate-100">
            Si necesitas funcionalidades específicas, puedo crear una solución personalizada para tu negocio.
          </p>
          <div class="mt-6 text-[12px] text-brand-300 leading-relaxed space-y-2">
            <p>
              ✨ <strong>Transparencia desde el día uno:</strong> Cada proyecto se cotiza con alcance y objetivos claros. Escríbeme y
              diseñemos la solución ideal para tu negocio.
            </p>
            <p class="opacity-90">
              • <strong>Materiales:</strong> Trabajamos con tu logotipo e imágenes existentes (no incluye diseño de identidad visual o
              ilustraciones desde cero).<br />
              • <strong>Dominio y Hosting:</strong> No van incluidos en el desarrollo base, pero al contratar nuestro
              <strong>plan de mantenimiento</strong> te olvidas de ello: incluye hosting, dominio y soporte continuo.<br />
              • <strong>Garantía:</strong> Incluye 1 ronda de cambios tras la entrega. Cambios o secciones adicionales posteriores se
              cotizan de forma independiente.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
