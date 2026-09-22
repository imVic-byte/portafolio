<template>
  <div class="rounded-2xl bg-[#09090c]/90 border border-white/5 p-6 sm:p-7 font-mono text-xs backdrop-blur-xl">
    <div class="flex flex-col sm:flex-row sm:items-center justify-between pb-4 mb-4 border-b border-white/5 gap-2">
      <div class="flex items-center gap-2.5">
        <span class="w-2 h-2 rounded-full bg-red-500 shadow-[0_0_8px_#ff2e2e]"></span>
        <span class="text-white font-bold tracking-tight">GARANTÍA TÉCNICA DE CALIDAD PARA TU INVERSIÓN</span>
      </div>
      <div class="flex items-center gap-2 text-[11px] text-zinc-400">
        <span>ESTÁNDAR:</span>
        <span class="text-red-400 font-semibold">ALTA DISPONIBILIDAD &amp; SEGURIDAD</span>
      </div>
    </div>

    <!-- Pestañas de Inspección Arquitectónica -->
    <div class="flex flex-wrap gap-2 mb-4">
      <button
        v-for="tab in tabs"
        :key="tab.id"
        type="button"
        @click="activeTab = tab.id"
        class="px-3.5 py-1.5 rounded-lg text-xs transition-all font-mono"
        :class="[
          activeTab === tab.id
            ? 'bg-[#030304] border border-red-500/50 text-red-400 font-semibold shadow-[0_0_15px_-3px_rgba(239,68,68,0.25)]'
            : 'bg-[#030304]/60 border border-white/5 text-zinc-400 hover:text-zinc-200 hover:border-white/20'
        ]"
      >
        {{ tab.label }}
      </button>
    </div>

    <!-- Salida de Datos Técnicos con traducción directa al beneficio del negocio -->
    <div class="p-4 sm:p-5 rounded-xl bg-[#030304] border border-white/5 text-[11px] leading-relaxed overflow-x-auto text-zinc-300">
      <div v-if="activeTab === 'edge'" class="space-y-2">
        <span class="text-zinc-500">// Infraestructura Perimetral: ¿Qué significa para tu negocio?</span>
        <div><span class="text-red-400 font-bold">Carga Inmediata:</span> "Menos de 1s en cualquier celular. Los clientes no abandonan tu carta."</div>
        <div><span class="text-red-400 font-bold">Cero Caídas:</span> "Red mundial distribuida: tu sistema no colapsa en horas punta."</div>
        <div><span class="text-red-400 font-bold">Hosting Optimizado:</span> "Sin cobros abusivos por servidores sobredimensionados. Eficiencia cloud pura."</div>
        <div><span class="text-red-400 font-bold">Actualización Instantánea:</span> "Cambias un precio o agotas un producto y se actualiza al segundo."</div>
      </div>

      <div v-else-if="activeTab === 'multitenant'" class="space-y-2">
        <span class="text-zinc-500">// Protección de Datos: ¿Qué significa para tu negocio?</span>
        <div><span class="text-red-400 font-bold">Privacidad Absoluta:</span> "Tus listas de clientes, compras y precios están blindadas bajo llave."</div>
        <div><span class="text-red-400 font-bold">Separación de Sucursales:</span> "Cada local o taller opera en su propio espacio privado sin confusiones."</div>
        <div><span class="text-red-400 font-bold">Control de Empleados:</span> "Cada usuario ve solo lo que necesita (cajero, garzón, mecánico, dueño)."</div>
        <div><span class="text-red-400 font-bold">Copias de Respaldo:</span> "Respaldos automáticos diarios. Tu contabilidad nunca se pierde."</div>
      </div>

      <div v-else-if="activeTab === 'automation'" class="space-y-2">
        <span class="text-zinc-500">// Automatización Operativa: ¿Qué significa para tu negocio?</span>
        <div><span class="text-red-400 font-bold">Presupuestos en 3 Segundos:</span> "Generación de PDF formal con tu logo y envío por WhatsApp en 1 clic."</div>
        <div><span class="text-red-400 font-bold">Descuento de Stock en Vivo:</span> "Se usa un repuesto y se resta del inventario al instante con alertas."</div>
        <div><span class="text-red-400 font-bold">Conexión con tu Local:</span> "Integración con impresoras térmicas de comandas, sensores y lectores."</div>
        <div><span class="text-red-400 font-bold">Ahorro de Horas Hombre:</span> "Elimina cientos de horas de tipeo manual y planillas enredadas de Excel."</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tabs = [
  { id: 'edge', label: 'Velocidad & Ahorro de Servidores' },
  { id: 'multitenant', label: 'Blindaje de Datos & Sucursales' },
  { id: 'automation', label: 'Automatización & WhatsApp' }
];

const activeTab = ref('edge');
</script>
