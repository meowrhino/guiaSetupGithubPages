# Checklist de traspaso

Lista de verificación para no olvidar nada al entregar una web a un cliente.
La guía del cliente (paso a paso del setup) vive en `index.html`; este archivo es **solo para mí**.

---

## 1. Antes de empezar el proyecto

- [ ] Definir con el cliente: dominio, contenidos, contacto, ¿necesita email en el dominio?
- [ ] ¿Va a haber formularios? → decidir servicio (Formspree, Web3Forms, etc.)
- [ ] ¿Va a haber analítica? → decidir servicio (Plausible, Umami, GA4) o ninguna

---

## 2. Durante el desarrollo — contenido del repo

### `<head>` de cada `.html`
- [ ] `<title>` único por página
- [ ] `<meta name="description">`
- [ ] `<meta name="author">`
- [ ] `<meta name="keywords">` (opcional pero recomendable)
- [ ] `<meta name="theme-color">`
- [ ] `<link rel="canonical">` con URL absoluta
- [ ] Open Graph: `og:title`, `og:description`, `og:image`, `og:url`, `og:type`, `og:site_name`, `og:locale`
- [ ] Twitter Card: `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
- [ ] Favicon multi-tamaño (`favicon.ico`, `32x32`, `16x16`, `apple-touch-icon`)
- [ ] JSON-LD structured data si aplica (Person, LocalBusiness, Organization)

### Archivos en la raíz del repo
- [ ] `robots.txt`
- [ ] `sitemap.xml`
- [ ] `404.html` — para evitar el 404 genérico feo de GitHub Pages
- [ ] `.nojekyll` si el proyecto tiene carpetas que empiezan por `_`
- [ ] `.gitignore` razonable (`.DS_Store`, `.vscode/`, etc.)
- [ ] `README.md` mínimo (nombre del proyecto + link a la web)
- [ ] `MANTENIMIENTO.md` con todo lo específico del proyecto (ver sección 4)

### Código y assets
- [ ] Rutas **relativas** (para que funcione en localhost, `usuario.github.io/repo` y dominio propio)
- [ ] Imágenes optimizadas (`.webp` cuando se pueda, pesos razonables)
- [ ] Vídeos comprimidos y con fallback para Safari si usan alpha
- [ ] Fuentes con `preconnect` si son de Google Fonts
- [ ] Sin `console.log` ni código muerto

---

## 3. Verificaciones funcionales antes de entregar

- [ ] Todas las páginas cargan sin errores en consola
- [ ] Todos los links internos funcionan
- [ ] Todos los links externos abren en nueva pestaña (`target="_blank" rel="noopener"`)
- [ ] Formularios probados de punta a punta (envío real + llegada del mail)
- [ ] Responsive probado en móvil, tablet y desktop
- [ ] Probado en Chrome, Safari y Firefox mínimo
- [ ] Preview de OG/Twitter Card revisado (https://www.opengraph.xyz o similar)
- [ ] Favicon se ve correctamente en pestaña
- [ ] Lighthouse rápido: performance, accesibilidad, SEO sin rojos grandes

---

## 4. `MANTENIMIENTO.md` del proyecto

Debe vivir dentro del repo del cliente. Cubrir:
- [ ] Estructura del repo (qué archivo hace qué)
- [ ] Qué archivos **sí** se tocan (normalmente `data.json`, imágenes, textos) y cuáles **no**
- [ ] Cómo añadir/modificar/borrar cada tipo de contenido, con ejemplos
- [ ] Formatos recomendados de imagen/vídeo
- [ ] Errores comunes y cómo arreglarlos
- [ ] Cómo cambiar info SEO (title, description, OG image)
- [ ] Credenciales de servicios externos si los hay (Formspree, etc.) — si no, dejar hueco para que las meta el cliente
- [ ] Contacto mío por si algo rompe

---

## 5. Entrega al cliente

- [ ] Cliente ha creado su cuenta de GitHub
- [ ] Cliente ha creado su cuenta de Cloudflare (si aplica dominio propio)
- [ ] Cliente tiene su dominio comprado (o sabe dónde comprarlo)
- [ ] Le envío un zip con **todo el contenido del repo** (incluido `MANTENIMIENTO.md`, `robots.txt`, `sitemap.xml`, `404.html`, `CNAME` no — ese lo genera GitHub)
- [ ] Le paso el link a la guía de setup: https://meowrhino.github.io/guiaSetupGithubPages/
- [ ] Acordamos sesión para hacer el setup juntos (o lo hago yo con sus credenciales delante)

---

## 6. Post-entrega

- [ ] Verificar que la web carga en `usuario.github.io/repo`
- [ ] Verificar que carga en el dominio propio (si aplica)
- [ ] Verificar HTTPS activo (candado en el navegador)
- [ ] Verificar `www.dominio.com` también redirige bien
- [ ] Probar formularios desde el dominio final (a veces CORS cambia al pasar de local a prod)
- [ ] Enviar email de traspaso al cliente con:
  - URL de la web
  - Link a `MANTENIMIENTO.md` dentro de su repo
  - Link a la guía de setup por si la necesita
  - Recordatorio de que el `CNAME` no se toca
