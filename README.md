# Portafolio Profesional de Ingeniería de Software & Ciberseguridad

Portafolio web técnico, comercial y de ultra alto rendimiento desarrollado con **Astro v7**, **Vue 3** (Composition API) y **Tailwind CSS v4**, diseñado bajo la estética **Obsidian & Crimson Tech** con arquitectura **Bento Grid** y optimizado para despliegues perimetrales en **Cloudflare Pages**.

---

## ⚡ Stack Tecnológico

- **Framework Principal:** [Astro v7](https://astro.build/) (Compilación SSG estática de alto rendimiento, cero JavaScript innecesario en el cliente).
- **Framework UI Interactivo:** [Vue 3](https://vuejs.org/) (Composition API en islas de hidratación diferida con directiva `client:visible`).
- **Motor de Estilos:** [Tailwind CSS v4](https://tailwindcss.com/) (`@tailwindcss/vite`, Dark Mode estricto, variables de diseño Obsidian & Crimson).
- **Tipografías Técnicas:** `@fontsource/space-grotesk` (Encabezados técnicos, `tracking-tight`, `font-bold`) y `@fontsource/inter` (Lectura y datos técnicos).
- **Despliegue Objetivo:** [Cloudflare Pages](https://pages.cloudflare.com/) (Distribución perimetral global Anycast, latencia sub-50ms).

---

## 🎨 Sistema de Diseño (Obsidian & Crimson Tech)

- **Fondo principal:** Obsidiana pura `#030304` con sutil cuadrícula de arquitectura técnica.
- **Bento Boxes / Tarjetas:** Vidrio obsidiana (`obsidian-card`) con bordes de precisión `border-white/10` y resplandor carmesí difuso.
- **Texto Principal:** Blanco puro (`text-white`) con gradientes en rojo/carmesí (`from-red-500 via-rose-500 to-red-400`).
- **Color de Acento:** Carmesí Neón (`#ef4444` / `#ff2e2e`), transmitiendo velocidad, potencia y rigor en ciberseguridad.

---

## 🚀 Proyectos Reales en Producción

1. **ServiML (La Serena, Chile) — [Google: 4.8★]**
   - Sistema de gestión integral para taller automotriz, flotas corporativas y climatización / maquinaria pesada.
   - Desarrollado a medida en 2 meses con dashboards por rol (mecánico, recepción, administración), trazabilidad por patente y envío automático de cotizaciones PDF por WhatsApp.

2. **neutroTransmisiones (Mecánica de Precisión)**
   - Software a medida en 2 meses para gestión y despiece técnico de cajas de cambio automáticas y manuales por etapas.
   - Control de inventario de repuestos críticos y cotizaciones en PDF con aprobación directa por WhatsApp.

---

## 📂 Estructura del Código

```text
Portafolio/
├── public/
│   ├── _headers            # Cabeceras de seguridad HTTP y caché inmutable para Cloudflare Pages
│   ├── favicon.svg         # Favicon vectorial
│   └── logo.webp           # Isotipo oficial circular del gato blanco
├── src/
│   ├── components/
│   │   ├── Header.astro    # Barra de navegación, logo oficial y accesos a WhatsApp e Instagram
│   │   ├── Hero.astro      # Gancho comercial: "Hablemos de tu Negocio, No de Tecnicismos"
│   │   ├── AboutMe.astro   # Sobre Mí, enfoque de ingeniería, filosofía ágil y métricas
│   │   ├── BentoGrid.astro # Tarjetas modulares: Perfil, Cloud eficiente y Ciberseguridad
│   │   ├── Projects.astro  # Casos reales en producción en 2 columnas (ServiML & neutroTransmisiones)
│   │   ├── Footer.astro    # Conversión final multicanal (WhatsApp, Correo, Instagram)
│   │   └── interactive/
│   │       ├── ArchitectureTelemetry.vue # Telemetría de edge, multi-tenant y bajo consumo
│   │       └── QuickContactGenerator.vue # Configurador interactivo de consultas a WhatsApp (+56937508655)
│   ├── layouts/
│   │   └── Layout.astro    # Layout base con SEO técnico, OpenGraph y background grid
│   ├── styles/
│   │   └── global.css      # Importación de fuentes, tokens y utilidades
│   └── pages/
│       └── index.astro     # Página principal ensamblada con arquitectura de islas
├── astro.config.mjs        # Configuración Astro + Vue + Tailwind v4 Vite
├── package.json
└── tsconfig.json
```

---

## 🚀 Comandos Disponibles

```bash
# Instalar dependencias
npm install

# Modo desarrollo local
npm run dev

# Verificación de tipos y diagnóstico
npx astro check

# Compilar para producción (genera carpeta dist/)
npm run build

# Vista previa de la compilación local
npm run preview
```

---

## ☁️ Despliegue en Cloudflare Pages

### Conexión Git (Recomendada)
1. Conecta este repositorio en el panel de **Cloudflare Dashboard > Workers & Pages > Create application > Pages > Connect to Git**.
2. Parámetros de compilación:
   - **Framework preset:** `Astro`
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
   - **Node.js Version:** `20` o superior.

---

## 📬 Canales de Contacto Oficiales
- **WhatsApp:** [+56 9 3750 8655](https://wa.me/56937508655)
- **Instagram:** [@im.vicnad](https://instagram.com/im.vicnad)
- **Correo Laboral:** [vic.d.nav@hotmail.com](mailto:vic.d.nav@hotmail.com)
