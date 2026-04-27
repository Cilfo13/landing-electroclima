# Electroclima

Landing page de captura de leads para Electroclima — SaaS de gestión para técnicos de climatización.

## Stack

- [Astro](https://astro.build) (output estático)
- CSS vanilla con variables custom
- Sin dependencias de UI framework

## Desarrollo local

```bash
npm install
npm run dev
```

Abre [http://localhost:4321](http://localhost:4321)

## Build de producción

```bash
npm run build
```

La carpeta `dist/` contiene el sitio estático listo para servir.

## Deploy en Vercel

### Opción A — Vercel CLI

```bash
npm i -g vercel
vercel
```

### Opción B — Vercel Dashboard

1. Subí este proyecto a un repositorio en GitHub
2. Entrá a [vercel.com](https://vercel.com) → **Add New Project**
3. Importá el repositorio
4. Vercel detecta Astro automáticamente; los defaults son correctos:
   - **Build Command:** `npm run build`
   - **Output Directory:** `dist`
5. Click **Deploy** → listo ✓

## Personalización rápida

| Qué cambiar | Dónde |
|---|---|
| Texto del hero | `src/components/Hero.astro` |
| Número de técnicos en espera | `src/components/Hero.astro` → `.social-proof span` |
| Colores | `src/styles/global.css` → `:root` |
| Link de WhatsApp | `src/components/CTAForm.astro` y `src/components/Footer.astro` |
| Email de contacto | `src/components/Footer.astro` |
| Dominio del sitio | `astro.config.mjs` → `site` |

## Conectar el formulario

El formulario actualmente maneja el estado en el cliente (muestra mensaje de éxito).
Para capturar los leads en producción, recomendamos:

- **[Formspree](https://formspree.io)** — gratis hasta 50 submissions/mes
- **[Resend](https://resend.com)** — envío de emails via API
- **Vercel KV / Supabase** — si querés guardar en base de datos

Cambiá el `action` del `<form>` en `CTAForm.astro` al endpoint correspondiente.
