# Push DE · envío 1 (Xacobeo 2027)

- **Mercado:** Alemania, Suiza y Austria · idioma alemán · trato de **Sie**.
- **Objetivo:** que el lector pida que le llamemos (Zoho Forms) y descubra dos rutas para 2027.
- **Base:** capturas de la campaña en español, traducidas y adaptadas al Brandbook 2027.

## Decisiones

- Sin enlace "Ver en el navegador".
- Cabecera: logo a la izquierda y "Web" a la derecha, ambos a `https://santiagoways.com/de/?utm_source=zoho_campaigns&utm_medium=newsletter&utm_campaign=push_de&utm_content=envio1`.
- Titular sobre la foto (provisional: montaje hórreo + peregrino; la foto definitiva está pendiente).
- CTA verde tras el texto y CTA blanco en la caja verde de cierre; ambos a Zoho Forms.
- Rutas a dos columnas (en móvil, una debajo de otra).
- Pie gris con logo verde, iconos propios (círculo verde Ways y glifo blanco) y textos legales.

## Imágenes para subir a Zoho (`img/`)

| Archivo | Se muestra a | Uso |
|---|---|---|
| `logo-santiago-ways.png` | 180 px (cabecera) y 150 px (pie) | Logo, PNG transparente |
| `hero-horreo-peregrino.jpg` | 600 × 420 px | Fondo del titular (provisional) |
| `ruta-sarria.jpg` | 260 px | Ruta 1 |
| `ruta-portugues.jpg` | 260 px | Ruta 2 |
| `icono-tiktok.png`, `icono-facebook.png`, `icono-youtube.png`, `icono-instagram.png` | 32 px | Redes |

## Enlaces aplicados

- Cabecera (logo y "Web"): web DE con UTM `push_de` / `envio1`.
- Botones "Rückruf anfordern" y "Ja, rufen Sie mich an": Zoho Forms `rueckruf`.
- Rutas: Ab Sarria y Camino Portugués (Küstenweg, ab Baiona), con UTM.
- Teléfonos: enlaces `tel:` en toda la tarjeta.
- Redes: TikTok (enlace a un vídeo), Facebook DE, YouTube, Instagram DE.

## Zoho

- Importación (Import/Upload HTML): `zoho/push-de-envio1.html` en la casilla del HTML y `zoho/imagenes.zip` (carpeta `images/`) en la casilla del zip. Las URLs de la librería de Zoho no sirven para importar.
- Nombre: `$[UD:FIRST_NAME||]$` (sin nombre queda «Hallo» y salto de línea).
- Baja y preferencias: `$[LI:UNSUBSCRIBE]$` y `$[LI:SUB_PREF]$`, el formato exacto que pide el importador.

## Asunto y preheader

- Asunto A: Camino 2027 zum Preis von heute
- Asunto B: Camino ohne Schlafsaal?
- Preheader: Gut schlafen, unbeschwert wandern. Wir kümmern uns um den Rest.

## Pendiente

- Foto principal definitiva (la actual es un montaje provisional).
- Prueba de envío a una lista de prueba (Gmail, Outlook y móvil).
