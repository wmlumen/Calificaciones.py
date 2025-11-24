# Escala de Calificaciones · Lista para Vercel

Aplicación 100 % estática que genera tablas oficiales de escalas de calificaciones y ofrece una calculadora para el alumno con modo de alto contraste y compatibilidad directa con impresión/PDF del navegador.

Todo vive en `index.html`, por lo que basta con copiarlo a `dist/` (lo hace `npm run build`) para desplegarlo como sitio estático.

## Requisitos

- [Node.js](https://nodejs.org/) 18 o superior
- Una cuenta de [Vercel](https://vercel.com/)
- (Opcional) [Vercel CLI](https://vercel.com/docs/cli) si prefieres desplegar desde la terminal

## Desarrollo local

```powershell
npm install
npm run dev
```

El comando anterior levanta un servidor estático en `http://localhost:4173`. Cualquier cambio sobre `index.html` se reflejará al recargar el navegador.

Para validar la estructura HTML antes de desplegar:

```powershell
npm run lint
```

## Características rápidas

- Generador de tablas oficial con algoritmo de límites y regla de residuos.
- Calculadora sincronizada con el nivel de exigencia configurado.
- Interfaz responsiva con modo de alto contraste accesible.
- Botón de impresión para exportar o guardar como PDF usando el navegador.

## Despliegue en Vercel

1. Importa el repo en [vercel.com](https://vercel.com/) o usa Vercel CLI.
2. Configura **Build Command** = `npm run build` y **Output Directory** = `dist` (coincide con `vercel.json`).
3. Publica. El fallback definido en `vercel.json` redirige cualquier ruta a `index.html`, así que puedes usar rutas limpias sin errores 404.

> Consejo: como el proyecto es estático, puedes activar **Deploy Hooks** o previews automáticas en cada pull request sin costos extra.

### Despliegue con Vercel CLI (opcional)

```powershell
npm run deploy
```

El comando construye la carpeta `dist/` y luego ejecuta `vercel --prod`, publicando la última versión y devolviendo la URL final.

## Estructura

- `index.html`: Aplicación completa (UI, estilos y lógica JS)
- `dist/`: Salida generada durante `npm run build` (se crea automáticamente)
- `vercel.json`: Configuración para servir el sitio estático con fallback de rutas limpias
- `package.json`: Scripts útiles para desarrollo, linting y despliegue
- `README.md`: Esta guía

## Personalización

- Actualiza los metadatos (`<title>`, `<meta description>`) en `index.html` para ajustar SEO.
- Si deseas añadir más activos (imágenes, fuentes, etc.), colócalos en la raíz y Vercel los servirá de forma estática.
- Para cambios de estilo mayores, considera extraer el CSS a un fichero separado y referenciarlo mediante `<link rel="stylesheet">`.

¡Lista para publicar! Cada push gatilla un preview en Vercel y, al promoverlo, la URL de producción se actualiza en segundos.
