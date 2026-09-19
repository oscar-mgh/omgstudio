<script setup>
import { ref } from 'vue';

const sent = ref(false);
const isSubmitting = ref(false);
const errorMessage = ref('');

const formData = ref({
  name: '',
  email: '',
  message: '',
  botcheck: '', // Campo Honeypot para evitar Spam
});

const resetForm = () => {
  sent.value = false;
  errorMessage.value = '';
  formData.value = { name: '', email: '', message: '', botcheck: '' };
};

const handleSubmit = async () => {
  // Si el bot llenó el campo oculto, abortamos discretamente
  if (formData.value.botcheck) return;

  isSubmitting.value = true;
  errorMessage.value = '';

  try {
    const response = await fetch('https://api.web3forms.com/submit', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        Accept: 'application/json',
      },
      body: JSON.stringify({
        access_key: import.meta.env.VITE_WEB3FORMS_KEY,
        name: formData.value.name.trim(),
        email: formData.value.email.trim(),
        message: formData.value.message.trim(),
        subject: `Prospección de web para ${formData.value.name}`,
      }),
    });

    const result = await response.json();

    if (result.success) {
      sent.value = true;
      formData.value = { name: '', email: '', message: '', botcheck: '' };
    } else {
      errorMessage.value = result.message || 'Ocurrió un error al enviar. Intenta de nuevo.';
    }
  } catch (error) {
    errorMessage.value = 'Error de conexión. Intenta nuevamente.';
  } finally {
    isSubmitting.value = false;
  }
};
</script>

<template>
  <section
    id="contacto"
    class="bg-slate-700 px-9 py-20 text-white lg:py-28">
    <div class="mx-auto grid max-w-[1150px] items-center gap-10 lg:grid-cols-[1fr_.88fr] lg:gap-[10%]">
      <div>
        <p class="mb-[18px] font-mono text-[11px] uppercase tracking-[.09em] text-slate-100">Hagamos que pase</p>
        <h2 class="mb-5 text-[clamp(2rem,3.7vw,3.8rem)] font-bold leading-tight tracking-[-.055em]">
          ¿Listo para que tu negocio <em class="font-sans not-italic font-extrabold text-slate-100">se vea increíble?</em>
        </h2>
        <p class="max-w-[470px] leading-7 text-slate-100">
          Cuéntame qué tienes en mente. Te responderé para conocer tu proyecto y proponerte el mejor camino.
        </p>
        <a
          class="mt-6 inline-flex min-h-12 items-center gap-2 rounded bg-[#25D366] px-[18px] font-bold text-white shadow-lg transition hover:-translate-y-0.5 hover:bg-[#1ebe5d]"
          href="https://wa.me/527201228939"
          target="_blank"
          rel="noopener">
          <svg
            aria-hidden="true"
            class="h-[22px] w-[22px]"
            viewBox="0 0 24 24"
            fill="currentColor">
            <path
              d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.572-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.05 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z" />
          </svg>
          <span>WhatsApp</span>
        </a>
      </div>

      <form
        class="bg-brand-700 p-6 shadow-[9px_9px_0_#080a1a] sm:p-8"
        @submit.prevent="handleSubmit">
        <Transition
          name="fade"
          mode="out-in">
          <div
            v-if="sent"
            key="success"
            class="grid min-h-[304px] place-content-center text-center">
            <span class="mx-auto mb-4 grid h-11 w-11 place-items-center rounded-full bg-brand-300 text-brand-950">✓</span>
            <h3 class="mb-2 text-xl font-bold">¡Mensaje listo!</h3>
            <p class="mx-auto mb-5 max-w-[255px] text-sm leading-relaxed text-brand-300">
              Gracias por escribirme. Me pondré en contacto contigo pronto.
            </p>
            <button
              class="min-h-11 border border-brand-400 px-5 text-sm font-bold hover:bg-brand-600"
              type="button"
              @click="resetForm">
              Enviar otro mensaje
            </button>
          </div>

          <div
            v-else
            key="form"
            class="grid gap-4">
            <!-- Campo Honeypot Oculto (Anti-Spam) -->
            <input
              v-model="formData.botcheck"
              type="checkbox"
              class="hidden"
              style="display: none" />

            <label class="grid gap-2 font-mono text-[10px] uppercase tracking-wide text-brand-300">
              Nombre
              <input
                v-model="formData.name"
                class="border-0 border-b border-brand-600 bg-transparent py-2 text-sm text-slate-100 outline-none placeholder:text-brand-400 focus:border-brand-300"
                required
                type="text"
                placeholder="¿Cómo te llamas?" />
            </label>

            <label class="grid gap-2 font-mono text-[10px] uppercase tracking-wide text-brand-300">
              Correo electrónico
              <input
                v-model="formData.email"
                class="border-0 border-b border-brand-600 bg-transparent py-2 text-sm text-slate-100 outline-none placeholder:text-brand-400 focus:border-brand-300"
                required
                type="email"
                placeholder="tu@correo.com" />
            </label>

            <label class="grid gap-2 font-mono text-[10px] uppercase tracking-wide text-brand-300">
              Cuéntame sobre tu proyecto
              <textarea
                v-model="formData.message"
                class="resize-y border-0 border-b border-brand-600 bg-transparent py-2 text-sm text-slate-100 outline-none placeholder:text-brand-400 focus:border-brand-300"
                required
                rows="3"
                placeholder="¿Qué necesitas crear?"></textarea>
            </label>

            <p
              v-if="errorMessage"
              class="text-xs font-sans text-red-300">
              {{ errorMessage }}
            </p>

            <button
              class="mt-2 inline-flex min-h-[51px] items-center justify-center gap-4 bg-brand-300 px-5 text-sm font-bold text-brand-950 transition hover:bg-slate-200 disabled:opacity-50 cursor-pointer"
              type="submit"
              :disabled="isSubmitting">
              {{ isSubmitting ? 'Enviando...' : 'Enviar mensaje' }}
            </button>
          </div>
        </Transition>
      </form>
    </div>
  </section>
</template>
