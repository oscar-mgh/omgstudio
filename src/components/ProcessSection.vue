<script setup>
const steps = [
  ['01', 'Cuéntame tu idea', 'Hablamos de tu negocio, objetivos y lo que necesita tu proyecto.'],
  ['02', 'Diseñamos contigo', 'Creo una propuesta visual pensada para tu marca y tus clientes.'],
  ['03', 'Lo hacemos realidad', 'Desarrollo un sitio rápido, funcional y adaptable a cualquier pantalla.'],
  ['04', 'Lanzamos', 'Configuramos todo y publicamos tu sitio para que empiece a trabajar por ti.'],
];
</script>

<template>
  <section
    id="proceso"
    class="bg-brand-950 px-9 py-20 lg:py-28">
    <div class="mx-auto max-w-[1150px]">
      <div class="mx-auto max-w-[760px] text-center">
        <p class="mb-[18px] font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">Simple y sin complicaciones</p>
        <h2 class="mb-5 text-[clamp(2rem,3.7vw,3.8rem)] font-bold leading-tight tracking-[-.055em]">
          De la idea a tu sitio <em class="font-sans not-italic font-extrabold text-brand-300">en cuatro pasos.</em>
        </h2>
      </div>
      <div class="my-12 grid gap-8 sm:grid-cols-2 lg:my-16 lg:grid-cols-4">
        <article
          v-for="step in steps"
          :key="step[0]"
          class="border-t border-brand-400 pt-4">
          <span class="font-mono text-xs text-brand-300">{{ step[0] }}</span>
          <h3 class="my-6 text-base font-bold">{{ step[1] }}</h3>
          <p class="text-sm leading-relaxed text-brand-300">{{ step[2] }}</p>
        </article>
      </div>
      <div class="grid gap-6 bg-brand-800 p-6 sm:grid-cols-[58px_1fr] sm:items-center lg:grid-cols-[70px_1fr_auto] lg:p-8">
        <div class="grid h-14 w-14 place-items-center bg-brand-300 text-2xl text-brand-950">✦</div>
        <div>
          <p class="mb-1 font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">Tu proyecto es único</p>
          <h3 class="mb-2 text-lg font-bold">Todos los sitios son desarrollados a medida.</h3>
          <p class="text-sm leading-relaxed text-slate-100">
            Si necesitas funcionalidades específicas, puedo crear una solución personalizada para tu negocio.
          </p>
          <p class="mt-5 text-[12px] text-brand-300">
            Cada proyecto se define con alcance y objetivos claros. Escríbeme para conocer la mejor solución. <br />
            No se incluye diseño de logotipos, branding o ilustraciones personalizadas (se integra logotipo e imágenes existentes).
            <br /><br />
            <strong>Importante:</strong> El precio del proyecto no incluye costo de hosting ni dominio. <br />
            Se incluye una ronda de ajustes relevantes sin costo adicional tras la entrega. Modificaciones posteriores aplican costo por
            tipo de cambio (ajustes de texto, visuales menores, nuevas secciones o funcionalidades).
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
