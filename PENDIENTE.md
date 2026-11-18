# Continuidad — web María José Reyes

**Estado (2026-11-18):** `index.html` reescrito con la estructura de la plantilla 21st.dev
«Fintech landing page template with flower meadow hero» (Lilac Meadow, MIT) adaptada a la identidad
de María José (crema/arena/oro/marrón, Cormorant Garamond + Jost + Sacramento, logo y monograma).
**Aún NO publicado**: la versión en https://caesar-dat-com.github.io/odonto-mj/ sigue siendo la anterior
(commit 68a75e3). César revisa y publica desde su repo. La versión anterior quedó en `index-anterior.html`.

Verificado el 2026-11-18 con Chrome headless: sin errores de consola, 56/56 planes, filtros, búsqueda,
orden, formato de precio, mensaje de WhatsApp y `mostrarPrecios:false` OK; también abre por `file://`.
Capturas: `capturas/plantilla-390x844.png`, `-1024x768.png`, `-1440x900.png`, `plantilla-completa-390.png`, `plantilla-completa-1440.png`.

## Marcadores EDITABLE que quedaron en `index.html`
1. **Testimonios** (`const TESTIMONIOS = []` en el `<script>` + comentario en la sección `#testimonios`):
   la sección está oculta hasta que se carguen testimonios **reales y autorizados**. No se inventó ninguno.
2. **Valores** (comentario antes de las 4 tarjetas): «Valoración personalizada», «Plan claro y por escrito»,
   «Agenda por WhatsApp», «Materiales de alta gama» siguen siendo redacción propuesta, no afirmaciones verificadas.
   Las fichas «Primero / Claridad / Cercanía / Calidad» son etiquetas decorativas nuevas: confirmar que gustan.
3. **Preguntas frecuentes** (comentario antes de `#preguntas`): las 6 respuestas reutilizan textos que ya
   estaban en el sitio; revisar con la doctora y ampliar si hace falta.
4. **Instagram** (comentario en el pie): dos enlaces a `https://instagram.com/` (icono y columna Contacto).

## Textos nuevos (no son datos, pero conviene que la doctora los apruebe)
- Título de la propuesta: «Cuatro frentes de trabajo, *un plan a tu medida*».
- Etiquetas de materiales en Tratamientos (p. ej. «Zirconio», «Disilicato de litio», «Pulido»), tomadas del catálogo.
- «Lo que puedes consultar directamente por WhatsApp» (franja) y «Antes de escribir» (título de preguntas).
- Globos al hacer clic en el medallón / diente del hero: «Agenda tu valoración» y «Tu sonrisa ✦».

## Pendiente
1. **Fotos reales** de la doctora / consultorio / antes-después: siguen sin existir. Si llegan, el lugar natural
   es el recuadro ilustrado de cada tratamiento (`.arte`) o una tarjeta junto a la propuesta.
2. Decisión de César: mantener `mostrarPrecios:true` o esconderlos.
3. Instagram real y, si los hay, testimonios reales.
4. Publicar (commit + push en el repo de César) cuando apruebe la versión nueva.
5. **Servidor LAN 8080**: la nota anterior decía que seguía encendido; no lo toqué (no es de esta tarea).
