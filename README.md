# Escala de Calificaciones · Despliegue en Vercel

Este repositorio contiene una aplicación web estática que genera tablas de escalas de calificaciones y permite a los alumnos calcular su nota según el nivel de exigencia definido.

La aplicación está empaquetada en `index.html`, no requiere backend y se publica como un sitio estático generando la carpeta `dist/` durante el build.

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

## Despliegue en Vercel

1. Inicia sesión en [vercel.com](https://vercel.com/) y crea un nuevo proyecto importando este repositorio desde GitHub.
2. En **Build & Output Settings** define:
	- **Build Command**: `npm run build`
	- **Output Directory**: `dist`
3. Pulsa **Deploy**. La configuración descrita en `vercel.json` generará un sitio estático y aplicará un fallback universal a `index.html` para manejar rutas limpias.

### Despliegue con Vercel CLI (opcional)

```powershell
npm run deploy
```

El comando construye la carpeta `dist/` y luego ejecuta `vercel --prod`, publicando la última versión y devolviendo la URL final.

## Estructura

- `index.html`: Aplicación completa (UI, estilos y lógica JS)
- `dist/`: Salida generada durante `npm run build` (se crea automáticamente)
- `vercel.json`: Configuración para servir el sitio estático con fallback de rutas
- `package.json`: Scripts útiles para desarrollo, linting y despliegue
- `README.md`: Esta guía

## Personalización

- Actualiza los metadatos (`<title>`, `<meta description>`) en `index.html` para ajustar SEO.
- Si deseas añadir más activos (imágenes, fuentes, etc.), colócalos en la raíz y Vercel los servirá de forma estática.
- Para cambios de estilo mayores, considera extraer el CSS a un fichero separado y referenciarlo mediante `<link rel="stylesheet">`.

¡Lista para publicar! Abre un pull request con tus ajustes y Vercel generará vistas previas automáticamente.
