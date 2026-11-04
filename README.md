# Orbix — Mi Compañero Estelar

Asistente personal con IA (estilo Jarvis), independiente de Lovable.

**Stack:** TanStack Start · React 19 · Supabase · OpenAI · Tailwind

## Requisitos

- Node.js 20+ (o Bun)
- Proyecto en [Supabase](https://supabase.com)
- API key de [OpenAI](https://platform.openai.com/api-keys)

## Configuración rápida

1. Clona el repo y entra a la carpeta:
   ```bash
   git clone https://github.com/alanjoablo1606-max/mi-companero-estelar.git
   cd mi-companero-estelar
   ```

2. Instala dependencias:
   ```bash
   npm install
   # o: bun install
   ```

3. Copia el ejemplo de variables de entorno:
   ```bash
   cp .env.example .env
   ```
   Rellena `SUPABASE_*` y `OPENAI_API_KEY` con tus valores.

4. En Supabase, ejecuta las migraciones SQL de `drizzle/migrations/` (SQL Editor) y crea el bucket de storage `jarvis-images` (privado).

5. Arranca en desarrollo:
   ```bash
   npm run dev
   ```
   Abre http://localhost:3000

## Auth con Google (opcional)

1. En [Google Cloud Console](https://console.cloud.google.com/) crea OAuth 2.0 (tipo Web).
2. En Supabase → Authentication → Providers → Google: pega Client ID y Secret.
3. Redirect URL de Supabase: `https://TU-PROYECTO.supabase.co/auth/v1/callback`

## Gmail / Calendar

En esta versión independiente las tools de Gmail y Calendar están desactivadas.
Para reactivarlas necesitas OAuth de Google con scopes de Gmail/Calendar y tokens del usuario (no se usa el connector-gateway de Lovable).

## Scripts

| Comando | Descripción |
|---------|-------------|
| `npm run dev` | Desarrollo |
| `npm run build` | Build de producción |
| `npm run preview` | Vista previa del build |
| `npm test` | Tests |

## Roadmap

Ver [roadmap.md](./roadmap.md).


## Instalar como app (PWA)

1. Publica el proyecto en HTTPS (Vercel, Netlify, etc.).
2. Abre la URL en el navegador del móvil o PC.
3. Instala:
   - **Android (Chrome):** menú ⋮ → *Instalar app* o *Añadir a pantalla de inicio*.
   - **iPhone (Safari):** Compartir → *Añadir a pantalla de inicio*.
   - **Windows / Mac (Chrome o Edge):** icono de instalar en la barra de direcciones.

El service worker está en `public/sw.js` y se registra al cargar la app.
