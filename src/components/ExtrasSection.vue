<template>
  <section
    id="adicionales"
    class="bg-brand-950 px-9 py-20 text-slate-100 lg:py-28">
    <div class="mx-auto grid max-w-[1150px] gap-10 lg:grid-cols-[40%_1fr] lg:gap-[8%]">
      <div class="max-w-[570px]">
        <p class="mb-[18px] font-mono text-[11px] uppercase tracking-[.09em] text-brand-300">Pasa de atraer visitas a cerrar ventas</p>
        <h2 class="mb-5 text-[clamp(2rem,3.7vw,3.8rem)] font-bold leading-tight tracking-[-.055em]">
          Funciones para llevar tu negocio <em class="font-sans not-italic font-extrabold text-brand-300">al siguiente nivel.</em>
        </h2>
        <p class="text-base leading-[1.8] text-brand-300">Integra lo que necesitas hoy y construye una base lista para el futuro.</p>
      </div>
      <div class="grid gap-4">
        <article class="grid gap-4 border border-brand-600/70 p-5 sm:grid-cols-[52px_1fr] sm:gap-5">
          <div class="grid h-12 w-12 place-items-center bg-brand-300 text-xl font-bold text-brand-950">$</div>
          <div>
            <div class="flex flex-col gap-2 sm:flex-row sm:items-baseline sm:justify-between">
              <h3 class="text-base font-bold">Pasarela de pago</h3>
              <strong class="text-sm text-brand-300">Comercio en línea</strong>
            </div>
            <p class="my-3 text-sm leading-relaxed text-brand-300">Vende directamente desde tu web con un proceso claro y seguro.</p>
            <ul class="flex flex-wrap gap-x-5 gap-y-2 text-xs text-slate-100">
              <li>✓ Mercado Pago o Stripe</li>
              <li>✓ Carrito y flujo de compra</li>
            </ul>
          </div>
        </article>
        <article class="grid gap-4 border border-brand-600/70 p-5 sm:grid-cols-[52px_1fr] sm:gap-5">
          <div class="grid h-12 w-12 place-items-center bg-brand-300 text-xl font-bold text-brand-950">◉</div>
          <div>
            <div class="flex flex-col gap-2 sm:flex-row sm:items-baseline sm:justify-between">
              <h3 class="text-base font-bold">Sistema de usuarios</h3>
              <strong class="text-sm text-brand-300">Área privada</strong>
            </div>
            <p class="my-3 text-sm leading-relaxed text-brand-300">Da a tus clientes una experiencia personalizada y práctica.</p>
            <ul class="flex flex-wrap gap-x-5 gap-y-2 text-xs text-slate-100">
              <li>✓ Registro, inicio de sesión y favoritos</li>
              <li>✓ Gestión y consulta de pedidos</li>
            </ul>
            <p class="mt-4 font-mono text-[10px] uppercase tracking-wide text-slate-200">Requiere VPS y base de datos.</p>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
