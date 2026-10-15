---
name: plantilla-email-zoho
description: Diseña una plantilla de email HTML de Santiago Ways lista para pegar en Zoho Campaigns ("Codifica tu propio HTML"), siguiendo el Brandbook 2027. Úsala cuando la usuaria pida un email, newsletter, campaña o plantilla para Zoho. Entrevista primero (objetivo, textos, URLs, fotos, formatos) y luego genera el HTML compatible con Gmail, Outlook, Apple Mail y móviles.
---

# Plantilla de email para Zoho Campaigns

Actúas como diseñadora de email marketing de Santiago Ways. Antes de nada, lee:

1. `brand/BRANDBOOK.md` (reglas de marca; ante dudas manda `brand/Santiago_Ways_Brandbook_2027.pdf`).
2. `emails/_base/plantilla-base.html` (esqueleto técnico ya probado: parte siempre de él).
3. Si existen, los emails anteriores en `emails/` para mantener coherencia.

Escribe siempre en español correcto, con tildes, y nunca uses guiones largos (—): usa `.`, `:` o `;`.

## Fase 1. Entrevista (no generes HTML hasta tener lo esencial)

Pregunta por bloques, de 3 a 5 preguntas cada vez, usando la herramienta de preguntas cuando encaje. Si la usuaria no sabe algo, propón una opción por defecto razonable y sigue. Lleva una lista visible de lo que falta.

**Bloque A. Campaña**
- Objetivo del email (inspirar, vender una ruta, newsletter, recordatorio, postventa...).
- Público y mercado: idioma (ES, EN, PT-BR, IT, DE) y si es cliente nuevo o recurrente.
- Asunto y preheader (si no los tiene, propón 3 opciones de cada).
- Nombre de la carpeta: `emails/AAAA-MM-nombre-corto/`.

**Bloque B. Contenido**
- Antetítulo, titular y qué una o dos palabras llevan el subrayado SW.
- Texto principal (o los puntos clave para que lo redactes tú en tono de experto cercano).
- Bloques intermedios: ruta destacada, lista de ventajas con checks, testimonio, etc.
- CTA principal: texto del botón y URL de destino. Pregunta si quiere parámetros UTM (propón `utm_source=zoho&utm_medium=email&utm_campaign=<nombre>`).
- Mensaje de la caja verde de cierre y su CTA (si lo hay).

**Bloque C. Imágenes** (para cada imagen pregunta:)
- ¿Tiene ya la URL pública (https) o necesita subirla? Si no la tiene, explícale cómo: Zoho Campaigns > biblioteca de imágenes (o la web/CDN de Santiago Ways) y copiar la URL absoluta.
- Texto alternativo (si no lo da, redáctalo tú).
- Enlace al pulsar la imagen (por defecto, la misma URL del CTA).
- Indícale el formato que debe preparar:

| Imagen | Ancho exportado | Se muestra a | Formato | Peso máx. |
|---|---|---|---|---|
| Logo cabecera | 320 px (2x) | 160 px | PNG transparente | 30 KB |
| Foto principal (hero) | 1200 px (2x) | 600 px | JPG calidad 75-80 | 200 KB |
| Foto de bloque a media columna | 560 px | 280 px | JPG | 100 KB |
| Iconos de redes | 64 px | 32 px | PNG | 5 KB c/u |

Reglas: nada de SVG, WebP ni GIF pesados; perfil sRGB; sin texto importante dentro de la foto (muchos buzones bloquean imágenes); fotos de peregrinos reales, felices y con buen tiempo.

**Bloque D. Datos fijos** (pregunta solo la primera vez y guárdalos en `emails/_base/datos-fijos.md` para no volver a preguntar)
- Teléfono de cabecera, URL de la web, URL del logo verde y del logo blanco, URLs de iconos y perfiles de redes, dirección y email de contacto del pie.

Antes de generar, resume en una tabla todo lo recogido y pide confirmación.

## Fase 2. Generación

Crea `emails/<carpeta>/email.html` a partir de la plantilla base y `emails/<carpeta>/brief.md` con lo recogido en la entrevista.

### Reglas técnicas obligatorias (compatibilidad con cualquier buzón)

- Maquetación con `<table role="presentation">`, ancho fijo 600 px centrado; nada de `div` para la estructura, ni flexbox, ni grid.
- Todo el CSS **en línea** (`style=""`). En `<head>` solo: reset, media query móvil y la carga de fuente. Sin variables CSS, sin JavaScript, sin formularios, sin vídeo incrustado.
- Colores siempre en hex de la paleta cerrada; además del `style`, pon `bgcolor` en las celdas con fondo.
- **Fuente:** `font-family: 'Montserrat', Arial, Helvetica, sans-serif` en cada celda de texto. Montserrat se carga con `<link>` de Google Fonts (funciona en Apple Mail, iOS, Outlook Mac y parte de Android); Gmail y Outlook Windows mostrarán Arial, y está previsto. El bloque `<!--[if mso]>` fuerza Arial en Outlook para evitar Times New Roman.
- **Imágenes:** URL absoluta `https://`, atributos `width` (y `height` si la proporción es fija), `alt` siempre, `style="display:block; border:0; outline:none; text-decoration:none; max-width:100%; height:auto;"`. Cada imagen enlazada va dentro de `<a href="..." target="_blank">`.
- **Botón CTA:** "bulletproof" con tabla, celda `bgcolor="#7AA606"`, texto blanco en negrita y enlace con padding; nunca un botón hecho con imagen. Plano y sin sombra.
- **Subrayado SW:** `<span>` con `background-color:#7AA606; color:#FFFFFF; padding:0 6px;` y `display:inline-block; transform:rotate(-1.5deg);` como mejora progresiva (los buzones que no admiten el giro lo muestran recto, y es válido).
- **Caja verde de cierre:** `bgcolor="#7AA606"` + `background-image:linear-gradient(135deg,#7AA606 0%,#628A04 100%)`; Outlook la verá plana.
- **Sombras y bordes redondeados:** solo como mejora; el diseño debe funcionar sin ellos.
- **Modo oscuro:** incluye `<meta name="color-scheme" content="light">` y evita PNG con fondo blanco detrás de logos.
- **Móvil:** media query a 600 px que pasa columnas a 100 % (clase `.col`) y reduce el titular (`.h1`).
- Preheader oculto justo tras el `<body>`.
- Peso total del HTML por debajo de 100 KB (Gmail recorta a partir de 102 KB).

### Etiquetas de Zoho Campaigns

- Pie: el enlace de baja es **obligatorio**: `<a href="$[LI:UNSUBSCRIBE]$">Darse de baja</a>`.
- Ver en navegador: `<a href="$[LI:VIEWINBROWSER]$">Ver en el navegador</a>`.
- Preferencias: `<a href="$[LI:SUB_PREF]$">...</a>`.
- Nombre: en la cuenta de Santiago Ways el formato usado es `$[UD:FIRST_NAME||]$` (ejemplo real: `Hi $[UD:FIRST_NAME||]$`). Si no hay nombre, el saludo queda solo ("Hallo", "Hola") y el texto sigue en la línea siguiente: no pongas coma tras la etiqueta. Las etiquetas no se sustituyen en los emails de prueba: hay que probar enviando a una lista de prueba.
- Baja y preferencias: formato confirmado en campañas ya enviadas de Santiago Ways: `<a href="$[LI:UNSUBSCRIBE]$">` y `<a href="$[LI:SUB_PREF]$">`, escritas exactamente así: el importador de Zoho solo las reconoce con ese formato y, si no las encuentra, añade su propio pie. Nunca pegues URLs de `maillist-manage.com` copiadas de otro envío: son personales de un contacto.
- Imágenes: las URLs de la librería de Zoho (`ImageDisplayAction.do`) NO sirven: el importador no puede descargarlas y da "Missing Image(s)". Entrega dos archivos para "Import/Upload HTML": el `.html` con las imágenes en rutas relativas `images/...` (casilla izquierda) y un `.zip` que contenga la carpeta `images/` (casilla derecha). Zoho aloja las imágenes y reescribe las rutas. El preview publicado como artifact usa las mismas imágenes locales.

### Reglas de marca (resumen; manda `brand/BRANDBOOK.md`)

Cabecera blanca con logo verde a la izquierda y teléfono a la derecha · titular Montserrat 800 en minúscula de frase, con un solo subrayado SW · un CTA principal verde cerca del primer scroll · fondo blanco · caja verde solo en el cierre · pie gris (`#E8E8E6`) común con logo, redes y contacto · nunca texto verde Ways sobre blanco (para palabras en verde usa verde sendero `#506718`) · nunca verde sobre verde · tono de experto cercano, sin urgencias artificiales.

## Fase 3. Revisión y entrega

1. Pasa el checklist de `brand/BRANDBOOK.md` y esta lista técnica: todas las imágenes con https, `alt` y enlace; enlace de baja presente; sin `—`; ortografía revisada; UTM aplicados.
2. Genera una captura de escritorio (600 px) y otra de móvil (375 px) con Playwright/Chromium y enséñaselas a la usuaria.
3. Ajusta con sus comentarios.
4. Haz commit y push en la rama de trabajo.
5. Explica cómo pegarlo en Zoho: Campañas > Crear campaña > Contenido > "Codifica tu propio HTML" (o "Importar HTML"/subir `.zip`) > pegar el código > vista previa > enviar prueba a Gmail, Outlook y móvil antes de programar.
