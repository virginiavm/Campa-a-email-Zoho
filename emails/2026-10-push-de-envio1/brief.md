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

- Imágenes: librería de Zoho Campaigns (`ImageDisplayAction.do`), las 8 aplicadas.
- Nombre: `$[UD:FIRST_NAME||]$`, formato de las campañas ya enviadas (sin nombre queda «Hallo» y salto de línea). Comprobar con una lista de prueba.
- Baja y preferencias: `http://$[li:unsubscribe]$` y `http://$[LI:SUB_PREF]$`, formato confirmado en una campaña ya enviada.

## Asunto y preheader

- Asunto A: Camino 2027 zum Preis von heute
- Asunto B: Camino ohne Schlafsaal?
- Preheader: Gut schlafen, unbeschwert wandern. Wir kümmern uns um den Rest.

## Pendiente

- Foto principal definitiva (la actual es un montaje provisional).
- Prueba de envío a una lista de prueba (Gmail, Outlook y móvil).
