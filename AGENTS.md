# Orbix — notas para agentes / desarrolladores

- Chat de IA: `src/routes/api/chat.ts` → `src/lib/ai/chat.server.ts`. Verifica el bearer token y la propiedad del hilo; guarda `UIMessage[]` en `threads.messages` en `onFinish`.
- Imágenes: bucket privado `jarvis-images` bajo `<userId>/`; las tools solo guardan la ruta y el cliente firma URLs.
- Voz: speech recognition/synthesis del navegador (`es-MX`).
- Gmail / Calendar: desactivados por defecto en la versión independiente. Requieren OAuth de Google propio (ver README).
- Stack: TanStack Start + React 19 + Supabase + OpenAI (Vercel AI SDK) + Tailwind.
