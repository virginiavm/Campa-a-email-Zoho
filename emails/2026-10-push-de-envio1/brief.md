# Push DE · envío 1 (Xacobeo 2027)

- **Mercado:** Alemania, Suiza y Austria · idioma alemán · trato de **Sie**.
- **Objetivo:** que el lector pida que le llamemos (Zoho Forms) y descubra dos rutas para 2027.
- **Base:** capturas de la campaña en español, traducidas y adaptadas al Brandbook 2027.

## Decisiones

- Sin enlace "Ver en el navegador".
- Cabecera: logo a la izquierda y el dominio «santiagoways.com» a la derecha, ambos a `https://santiagoways.com/de/?utm_source=zoho_campaigns&utm_medium=newsletter&utm_campaign=push_de&utm_content=envio1`.
- Titular en Montserrat integrado en la foto del hórreo (en espejo), con etiqueta «XACOBEO 2027».
- CTA verde tras el texto y CTA blanco en la caja verde de cierre; ambos a Zoho Forms.
- Rutas, ventajas y caja de cierre a dos o tres columnas, también en móvil.
- Pie gris con isotipo, redes, teléfonos de los 4 países, dirección y textos legales.
- Mejoras de diseño del brandbook (p. 30): texto inicial más corto, franja de ventajas con iconos en brote, línea verde corta sobre los títulos de sección, etiqueta niebla «XACOBEO 2027» en el hero, caja de nota en niebla.

## Imágenes para subir a Zoho (`img/`)

| Archivo | Se muestra a | Uso |
|---|---|---|
| `logo-santiago-ways.png` | 180 px (cabecera) y 150 px (pie) | Logo, PNG transparente |
| `hero-titular.jpg` | 600 × 320 px | Hero: hórreo (foto original en espejo) con titular en Montserrat y overlay suave |
| `ruta-sarria.jpg` | 260 px | Ruta 1 |
| `ruta-portugues.jpg` | 260 px | Ruta 2 |
| `icono-tiktok.png`, `icono-facebook.png`, `icono-youtube.png`, `icono-instagram.png` | 32 px | Redes |
| `ventaja-habitacion.png`, `ventaja-equipaje.png`, `ventaja-asistencia.png` | 56 px | Franja «So reisen Sie mit uns» |
| `isotipo-santiago-ways.png` | 40 px | Concha del pie |

## Enlaces aplicados

- Cabecera (logo y dominio «santiagoways.com»): web DE con UTM `push_de` / `envio1`.
- Botones "Rückruf anfordern" y "Ja, rufen Sie mich an": Zoho Forms `rueckruf`.
- Rutas: Ab Sarria y Camino Portugués (Küstenweg, ab Baiona), con UTM.
- Teléfonos: enlaces `tel:` en toda la tarjeta.
- Redes: TikTok (@santiagoways_en), Facebook DE, YouTube, Instagram DE.

## Zoho

- Importación (Import/Upload HTML): `zoho/push-de-envio1.html` en la casilla del HTML y `zoho/imagenes.zip` (carpeta `images/`) en la casilla del zip. Las URLs de la librería de Zoho no sirven para importar.
- Nombre: `$[UD:FIRST_NAME||]$` (sin nombre queda «Hallo» y salto de línea).
- Baja y preferencias: `$[LI:UNSUBSCRIBE]$` y `$[LI:SUB_PREF]$`, el formato exacto que pide el importador.

## Asunto y preheader

- Asunto A: Camino 2027 zum Preis von heute
- Asunto B: Camino ohne Schlafsaal?
- Preheader: Gut schlafen, unbeschwert wandern. Wir kümmern uns um den Rest.

## Pendiente

- Prueba de envío a una lista de prueba (Gmail, Outlook y móvil).
