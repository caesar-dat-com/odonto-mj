# Sitio web — María José Reyes · Rehabilitación Oral y Estética

Catálogo de planes con contacto directo por WhatsApp. Estático: solo HTML + CSS + JS en un único archivo, sin dependencias, sin build ni servidor (solo carga las fuentes de Google). Funciona con doble clic y servido desde GitHub Pages en un subdirectorio (todas las rutas son relativas).

## Archivos
- `index.html` — la página completa (estilos, ilustraciones SVG y datos dentro del mismo archivo). Diseño basado en la estructura de la plantilla «Lilac Meadow» (ver Créditos) con la identidad de María José.
- `index-anterior.html` — versión previa (estilo Apple + patrones 21st.dev), guardada antes de la reescritura del 2026-11-18.
- `img/logo.png`, `img/logo-blanco.png`, `img/monograma.png` — logo recortado con fondo transparente (extraído del PDF original). `img/logo.svg` — vectorización del logo.
- `material/` — material original recibido (logo en PDF y PNG).
- `capturas/` — pantallazos de referencia (`plantilla-*.png` son los del diseño nuevo).

## Estructura de la página (de arriba a abajo)
1. **Barra** fija con efecto cristal al bajar, enlaces y botón de WhatsApp (en móvil: menú desplegable).
2. **Hero «pradera»**: logo, título «Tu sonrisa, diseñada a tu medida», medallón dorado con el monograma y un diente perlado apoyados en una pradera floral crema/oro pintada con SVG (3 capas con profundidad, polen que sube, paralaje con el ratón; clic en el medallón o el diente = giro).
3. **Propuesta** («Cuatro frentes de trabajo…») + **4 tarjetas de valores**.
4. **Tratamientos**: 4 bloques texto + ilustración alternados (cada uno lleva al catálogo ya filtrado).
5. **Franja** de tratamientos que se pueden consultar.
6. **Testimonios** — oculta hasta que se carguen testimonios reales (ver abajo).
7. **Planes y tarifas**: catálogo con filtros, búsqueda, orden y aviso de valores de referencia.
8. **Tres pasos** para agendar · 9. **Preguntas** (acordeón) · 10. **Cierre** con pradera · 11. **Pie**.

## Cómo verlo
Doble clic en `index.html`, o servirlo:

    python3 -m http.server 8899 --bind 127.0.0.1   # http://127.0.0.1:8899

## Qué se edita (todo dentro del `<script>` al final de `index.html`)

### 1. Configuración
```js
const CONFIG = {
  whatsapp: "573176980998",  // número con indicativo, sin + ni espacios
  mostrarPrecios: true,      // false => se oculta TODO precio del catálogo (y la pregunta sobre precios)
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
- `destacado: true`: tarjeta oscura, sube en el orden; los dos primeros llevan la etiqueta «Más pedido»

Al tocar un plan se abre WhatsApp con el mensaje ya escrito:
«Hola Dra. María José, vi su página web y me interesa el plan *X* ($Y). ¿Me cuenta cómo agendar la valoración?»

Los textos «Ver los N planes» de la sección Tratamientos se cuentan solos a partir de `PLANES`.

### 3. Testimonios (opcional)
```js
const TESTIMONIOS = [];   // vacío => la sección no aparece
// {texto:"…", autor:"Nombre o iniciales", plan:"Diseño de sonrisa"}
```
Solo testimonios reales y con autorización de la paciente.

### 4. Instagram
En el pie hay dos enlaces a `https://instagram.com/` (icono y columna «Contacto»): reemplazar por el perfil real.

### 5. Colores de la pradera (avanzado)
`PRADERA_COLORES` (rampa de flores de oscuro a claro, color de bruma y de las pajas) y `CAPAS_PRADERA` (altura, montículos y densidad de cada capa). La pradera es determinista: cada `<svg data-pradera … data-semilla="N">` dibuja siempre lo mismo para la misma semilla.

## Accesibilidad y movimiento
Foco visible en todos los controles, enlace «Ir directo a los planes» al tabular, `alt` en las imágenes de contenido (las ilustraciones son decorativas, `aria-hidden`), contraste de texto ≥ 4.5:1 sobre crema y marrón. Con «reducir movimiento» activado en el sistema se apagan todas las animaciones (la pradera se dibuja igual, sin entrada ni polen).

## Pendiente / sugerido
Ver `PENDIENTE.md`.

Los precios provienen del tarifario «Precios odontología Majo y Guille» entregado como material; la página aclara que son valores de referencia y que el plan final se confirma en la valoración.

## Créditos
- Estructura, ritmo de secciones, pradera pintada y patrones de interacción adaptados de la plantilla «Fintech landing page template with flower meadow hero» (`lilac-meadow-landing`) de [21st.dev/@kedhareswer](https://21st.dev/@kedhareswer) (Kedhareswer Naidu), licencia MIT. Reescrita en HTML/CSS/JS sin React ni Tailwind; paleta, tipografías, logo y textos son de María José Reyes.
