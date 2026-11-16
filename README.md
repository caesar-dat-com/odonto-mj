# Sitio web — María José Reyes · Rehabilitación Oral y Estética

Catálogo de planes con contacto directo por WhatsApp. Estático: solo HTML + CSS + JS, sin dependencias ni servidor.

## Archivos
- `index.html` — la página completa (estilos y datos dentro del mismo archivo).
- `img/logo.png`, `img/logo-blanco.png`, `img/monograma.png` — logo recortado con fondo transparente (extraído del PDF original).
- `material/` — material original recibido (logo en PDF y PNG).
- `capturas/` — pantallazos de referencia.

## Cómo verlo
Doble clic en `index.html`, o servirlo:

    python3 -m http.server 8899 --bind 127.0.0.1   # http://127.0.0.1:8899

## Qué se edita (todo al final de `index.html`, dentro del `<script>`)

### 1. Configuración
```js
const CONFIG = {
  whatsapp: "573176980998",  // número con indicativo, sin + ni espacios
  mostrarPrecios: true,      // false => se oculta TODO precio del catálogo
  moneda: "COP"
};
```

### 2. Planes
Cada plan es una línea en el arreglo `PLANES`:

```js
{cat:"diseno", nombre:"Mini diseño monolítico · 6 bordes",
 incluye:"Limpieza + 3 sesiones de aclaramiento + 6 bordes incisales.",
 precio:1280000, destacado:true}
```
- `cat`: `diseno` | `estetica` | `rehabilitacion` | `mantenimiento`
- `precio`: número sin puntos ni símbolo (se formatea solo)
- `destacado: true`: lo marca como «Más pedido» y lo sube en el orden

Al tocar un plan se abre WhatsApp con el mensaje ya escrito:
«Hola Dra. María José, vi su página web y me interesa el plan *X* ($Y). ¿Me cuenta cómo agendar la valoración?»

### 3. Instagram
En el footer, reemplazar `https://instagram.com/` por el perfil real.

## Pendiente / sugerido
- **Fotos reales**: no hay ninguna foto de la doctora, el consultorio ni casos. Se pueden meter dentro de las tarjetas-arco de «Tratamientos» (reemplazar el `<svg class="ico">` por un `<img>`) y en el hero.
- Revisar los 4 textos de la franja de valores (valoración, plan escrito, agenda, materiales): son redacción propuesta, no afirmaciones verificadas.
- Decidir si los precios se muestran públicamente (`mostrarPrecios`).
- Publicación: sirve cualquier hosting estático (Netlify Drop, GitHub Pages, Cloudflare Pages) arrastrando esta carpeta.

Los precios provienen del tarifario «Precios odontología Majo y Guille» entregado como material; la página aclara que son valores de referencia y que el plan final se confirma en la valoración.
