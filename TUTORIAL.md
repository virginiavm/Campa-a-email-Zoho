# Tutorial: cómo pedir a Claude Code una plantilla de email para Zoho

Guía para empezar desde cero, sin experiencia previa en Claude Code ni en GitHub.

## 1. La idea en una frase

Este repositorio es tu "proyecto de Claude Chat", pero mejor: todo lo que en un proyecto pondrías como instrucciones y archivos de conocimiento vive aquí, en carpetas, y Claude lo lee solo cada vez que abres una sesión.

| En un proyecto de Claude Chat | Aquí, en Claude Code |
|---|---|
| Instrucciones del proyecto | `CLAUDE.md` (se carga siempre) |
| Archivos de conocimiento | `brand/` (brandbook PDF, resumen y colores) |
| "Prompt" que repites cada vez | La skill `/plantilla-email-zoho` |
| Conversaciones sueltas | Cada email queda guardado en `emails/` con su historial |

## 2. Vocabulario mínimo de GitHub

- **Repositorio (repo):** la carpeta del proyecto en la nube. El tuyo: `virginiavm/Campa-a-email-Zoho`.
- **Rama (branch):** una copia de trabajo. Claude trabaja en una rama para no tocar la versión principal (`main`).
- **Commit:** una "foto" guardada de los cambios, con un mensaje.
- **Push:** subir esos commits a GitHub.
- **Pull request (PR):** la petición de pasar los cambios de una rama a `main`. Cuando un email esté aprobado, pide a Claude: "abre un PR" y luego pulsas *Merge* en GitHub.

No necesitas escribir comandos: pídeselo a Claude en lenguaje normal.

## 3. Qué hay ya preparado

```
CLAUDE.md                               instrucciones permanentes (marca y redacción)
brand/                                  brandbook y tokens de diseño
.claude/skills/plantilla-email-zoho/    el "asistente de emails": entrevista, reglas técnicas y entrega
emails/_base/plantilla-base.html        esqueleto HTML compatible con Gmail, Outlook, Apple Mail y móvil
emails/_base/datos-fijos.md             (se crea la primera vez) teléfono, logos, redes, pie
emails/AAAA-MM-nombre/                  cada campaña: email.html + brief.md + capturas
```

## 4. Cómo empezar cada email

1. Abre una sesión nueva en [claude.ai/code](https://claude.ai/code) con este repositorio seleccionado.
2. Escribe:

   ```
   /plantilla-email-zoho Quiero un email para lanzar el Camino Portugués de la costa en primavera
   ```

   (también funciona decir "hazme una plantilla de email para Zoho...").
3. Claude te entrevistará por bloques: objetivo, idioma, asunto, textos, CTA, URLs y fotos. Si no sabes algo, di "propón tú".
4. Te enseñará un resumen; confírmalo.
5. Genera el HTML, hace capturas de escritorio y móvil y te las enseña. Pide cambios con naturalidad: "el titular más corto", "cambia la foto 2".
6. Cuando te guste, guarda los cambios en GitHub (commit y push) y te dice dónde está el archivo.

La primera vez te preguntará los datos fijos (teléfono, logos, redes, dirección). Después ya no.

## 5. Cómo preparar las imágenes

Los buzones no pueden leer imágenes de tu ordenador: cada imagen necesita una **URL pública que empiece por `https://`**.

1. Exporta con estas medidas (el doble de lo que se ve, para que se vea nítido en pantallas retina):

   | Imagen | Exportar a | Formato | Peso máx. |
   |---|---|---|---|
   | Logo | 320 px de ancho | PNG transparente | 30 KB |
   | Foto principal | 1200 px de ancho | JPG calidad 75-80 | 200 KB |
   | Foto de media columna | 560 px de ancho | JPG | 100 KB |
   | Iconos de redes | 64 × 64 px | PNG | 5 KB |

   Nada de SVG ni WebP (Outlook y Gmail los fallan). No pongas texto importante dentro de las fotos: muchos clientes bloquean imágenes por defecto y el texto alternativo es lo único que se ve.
2. Súbelas a la biblioteca de imágenes de Zoho Campaigns (o a la web de Santiago Ways) y copia la URL de cada una.
3. Pásale a Claude las URLs. Claude añadirá a cada imagen su texto alternativo y su enlace.

## 6. Qué hace que el código funcione en cualquier buzón

No tienes que hacerlo tú; es lo que la skill obliga a Claude a respetar:

- Estructura con tablas de 600 px y estilos en línea (lo que mejor soportan Outlook y Gmail).
- Montserrat se carga desde Google Fonts; donde no se puede (Gmail, Outlook Windows) se ve Arial, de forma limpia y prevista.
- Botones hechos con código, no con imágenes: se ven aunque las imágenes estén bloqueadas.
- Todas las imágenes con `https`, ancho fijo, texto alternativo y enlace.
- Enlace de baja de Zoho (`$[LI:UNSUBSCRIBE]$`) y "ver en el navegador" (`$[LI:VIEWINBROWSER]$`) ya incluidos.
- Menos de 100 KB para que Gmail no recorte el email.

## 7. Cómo pegarlo en Zoho Campaigns

1. Abre el archivo `email.html` en la app de Claude o en GitHub y copia todo el código (o pídele a Claude: "dame el código para copiar").
2. En Zoho Campaigns: **Campañas > Crear campaña > Email** y rellena asunto, remitente y lista.
3. En **Contenido**, elige **"Codifica tu propio HTML"** (o "Importar HTML") y pega el código.
4. Si usas el nombre del contacto, sustituye `{{NOMBRE}}` con el botón **"Insertar etiqueta de combinación"** del editor.
5. Revisa la vista previa y **envía una prueba** a una cuenta de Gmail, una de Outlook y al móvil.
6. Si algo se ve mal, haz una captura y pásasela a Claude.

## 8. Frases útiles

- "Revisa este email con el checklist del brandbook."
- "Hazme la versión en inglés de `emails/2026-11-portugues`."
- "Usa como base el email de octubre pero con otra ruta."
- "Guarda los cambios y abre un pull request."
- "Añade este dato a los datos fijos: ..."
