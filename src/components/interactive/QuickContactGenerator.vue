<template>
  <div class="rounded-2xl bg-[#09090c]/90 border border-white/10 p-6 sm:p-9 backdrop-blur-xl">
    <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 pb-6 mb-6 border-b border-white/5">
      <div>
        <span class="text-xs font-mono text-red-400 uppercase tracking-wider block mb-1">
          CONFIGURADOR DIRECTO
        </span>
        <h3 class="text-xl sm:text-2xl font-bold text-white tracking-tight font-heading">
          Personaliza tu Consulta Comercial
        </h3>
      </div>
      <div class="flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-[#030304] border border-red-500/30 text-xs font-mono text-zinc-300">
        <span class="w-2 h-2 rounded-full bg-red-500 shadow-[0_0_6px_#ff2e2e]"></span>
        <span class="text-red-300 font-semibold">RESPUESTA DIRECTA VÍA WHATSAPP</span>
      </div>
    </div>

    <!-- Selección de Tipo de Solución -->
    <div class="space-y-4 mb-6">
      <label class="block text-xs font-mono text-zinc-400 uppercase">
        1. Selecciona la solución que necesitas para tu negocio:
      </label>
      <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
        <button
          v-for="option in projectTypes"
          :key="option.id"
          type="button"
          @click="selectedType = option.id"
          class="text-left p-4 rounded-xl border transition-all text-xs font-mono"
          :class="[
            selectedType === option.id
              ? 'bg-[#030304] border-red-500 text-white shadow-[0_0_20px_-4px_rgba(239,68,68,0.35)]'
              : 'bg-[#030304]/60 border-white/5 text-zinc-400 hover:border-white/20 hover:text-zinc-200'
          ]"
        >
          <div class="flex items-center justify-between mb-1.5">
            <span class="font-bold font-heading text-sm" :class="selectedType === option.id ? 'text-red-400' : 'text-zinc-200'">
              {{ option.name }}
            </span>
            <span v-if="selectedType === option.id" class="text-red-500 text-xs font-bold">●</span>
          </div>
          <p class="text-[11px] text-zinc-400 font-sans leading-relaxed">
            {{ option.description }}
          </p>
        </button>
      </div>
    </div>

    <!-- Campos de Contexto Rápido -->
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-6">
      <div>
        <label for="businessName" class="block text-xs font-mono text-zinc-400 uppercase mb-2">
          2. Nombre de tu negocio o empresa:
        </label>
        <input
          id="businessName"
          v-model="businessName"
          type="text"
          placeholder="Ej: Restobar Central / Empresa de Servicios / Local Comercial"
          class="w-full px-4 py-2.5 rounded-xl bg-[#030304] border border-white/10 text-white placeholder-zinc-500 text-xs font-mono focus:outline-none focus:border-red-500 focus:shadow-[0_0_15px_rgba(239,68,68,0.2)] transition-all"
        />
      </div>

      <div>
        <label class="block text-xs font-mono text-zinc-400 uppercase mb-2">
          3. ¿Qué problema necesitas resolver primero?:
        </label>
        <select
          v-model="selectedPriority"
          class="w-full px-4 py-2.5 rounded-xl bg-[#030304] border border-white/10 text-white text-xs font-mono focus:outline-none focus:border-red-500 focus:shadow-[0_0_15px_rgba(239,68,68,0.2)] transition-all"
        >
          <option value="Eliminar el papel/Excel y organizar la operación diaria">Eliminar el papel/Excel y organizar la operación diaria</option>
          <option value="Recibir reservas, pedidos o consultas de clientes en automático">Recibir reservas, pedidos o consultas de clientes en automático</option>
          <option value="Enviar presupuestos y comprobantes por WhatsApp en 1 clic">Enviar presupuestos y comprobantes por WhatsApp en 1 clic</option>
          <option value="Controlar stock de productos/repuestos y evitar mermas">Controlar stock de productos/repuestos y evitar mermas</option>
          <option value="Tener dashboards en vivo con métricas y facturación del negocio">Tener dashboards en vivo con métricas y facturación del negocio</option>
        </select>
      </div>
    </div>

    <!-- Vista Previa del Mensaje a Enviar -->
    <div class="mb-6 rounded-xl bg-[#030304] border border-white/5 p-4 sm:p-5 font-mono text-xs">
      <div class="flex items-center justify-between pb-2 mb-2 border-b border-white/5 text-[11px] text-zinc-400">
        <span>PREVIEW_WHATSAPP_MESSAGE</span>
        <span class="text-zinc-400 font-mono">+56 9 3750 8655</span>
      </div>
      <p class="text-zinc-300 whitespace-pre-line text-[11px] leading-relaxed select-all">
        {{ generatedMessage }}
      </p>
    </div>

    <!-- Botón de Envío Directo a WhatsApp -->
    <div class="flex flex-col sm:flex-row items-center justify-between gap-4">
      <div class="text-xs text-zinc-400 font-mono text-center sm:text-left">
        Sin intermediarios • Coordinación directa para demo técnica de 15 minutos
      </div>

      <a
        :href="whatsappUrl"
        target="_blank"
        rel="noopener noreferrer"
        class="w-full sm:w-auto btn-crimson-glow inline-flex items-center justify-center gap-2.5 px-7 py-3.5 rounded-xl font-bold text-sm tracking-tight font-heading"
      >
        <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
          <path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.462-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372s-1.04 1.016-1.04 2.479 1.065 2.876 1.213 3.074c.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/>
        </svg>
        <span>Agendar Demostración (WhatsApp)</span>
      </a>
    </div>

    <!-- Alternativas de Contacto Directo -->
    <div class="mt-5 pt-4 border-t border-white/5 flex flex-wrap items-center justify-between text-[11px] font-mono text-zinc-400 gap-2">
      <span>¿Prefieres otro canal directo?</span>
      <div class="flex items-center gap-4">
        <a href="mailto:vic.d.nav@hotmail.com" class="hover:text-red-400 transition-colors">
          ✉ vic.d.nav@hotmail.com
        </a>
        <a href="https://instagram.com/im.vicnad" target="_blank" rel="noopener noreferrer" class="hover:text-red-400 transition-colors">
          Instagram: @im.vicnad
        </a>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';

const phone = '56937508655';

const projectTypes = [
  {
    id: 'gestion',
    name: 'App de Gestión',
    description: 'Centralización de operaciones, inventario, roles de usuario, órdenes de servicio y dashboards en tiempo real para cualquier rubro comercial.'
  },
  {
    id: 'landing',
    name: 'Web Landing Interactiva',
    description: 'Sitio de alta velocidad y conversión con módulos interactivos según tu necesidad: carta digital con upselling, reservas o toma de pedidos.'
  },
  {
    id: 'custom',
    name: 'Sistema a Medida',
    description: 'Desarrollo completo desde cero adaptado a los flujos particulares de tu empresa: integraciones complejas, bots y cero costos fijos de servidor.'
  }
];

const selectedType = ref('gestion');
const businessName = ref('');
const selectedPriority = ref('Eliminar el papel/Excel y organizar la operación diaria');

const generatedMessage = computed(() => {
  const typeObj = projectTypes.find(t => t.id === selectedType.value);
  const typeTitle = typeObj ? typeObj.name : 'Sistema a Medida';
  const biz = businessName.value.trim() ? ` para mi negocio "${businessName.value.trim()}"` : '';

  return `Hola, estuve revisando tu portafolio de software.

Me gustaría coordinar una demostración rápida de:
• Tipo de Solución: ${typeTitle}${biz}
• Objetivo Principal: ${selectedPriority.value}

¿Podemos coordinar una llamada o demo de 15 minutos para ver cómo implementarlo? Muchas gracias.`;
});

const whatsappUrl = computed(() => {
  return `https://wa.me/${phone}?text=${encodeURIComponent(generatedMessage.value)}`;
});
</script>
