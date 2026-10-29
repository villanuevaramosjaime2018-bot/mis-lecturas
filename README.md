# 📚 Mis Lecturas

Tu compañero de lectura: dicta resúmenes y extractos de tus libros con la voz y guárdalos en tu Google Drive, un Google Doc por libro dentro de la carpeta **«Mis Lecturas»**.

**App:** https://villanuevaramosjaime2018-bot.github.io/mis-lecturas/

## Cómo instalarla en el celular
1. Abre el enlace en **Google Chrome** del celular.
2. Menú ⋮ → **Instalar app** (o «Agregar a la pantalla principal»).
3. Abre «Mis Lecturas», pulsa **Ingresar con Google** y acepta. Si aparece «Google no ha verificado esta app», toca **Continuar**: la app es tuya y está en modo de prueba.

## Comandos de voz
Toca el micrófono y di la orden (o activa **Manos libres** en el menú). Cada orden tiene también su botón.

| Di… | Qué hace |
|---|---|
| «Empezar» | Comienza a dictar (o empieza la lectura nueva) |
| «Parar» | Pausa el dictado o la lectura en voz alta |
| «Seguir agregando» | Reanuda el dictado |
| «Guardar» | Guarda el libro en tu Drive |
| «Escuchar» | Lee el resumen en voz alta |
| «Corregir» | Edita el texto con el teclado |
| «Descargar» | Descarga el libro en Word (.docx) |
| «Nueva lectura» | Registra otro libro |
| «Mis libros» | Abre tu lista de libros |
| «Abrir …» | Abre un libro por su título, p. ej. «Abrir Cien años de soledad» |
| «Continuar otro día» | Nueva sesión con fecha y hora, al final del mismo documento |
| «Volver» | Regresa a la pantalla anterior |

Truco: al dictar, puedes terminar una frase con «… parar» o «… guardar».

## Formato del Google Doc
- Título (Título 1), «Autor:», «Fecha de inicio:».
- Cada sesión con subtítulo **«Sesión – dd/mm/aaaa hh:mm»** (Título 2) y cada bloque dictado marcado con su hora `[hh:mm]`.
- Sin conexión, todo queda en el celular y se sube solo al volver la señal.

## Configuración de Google (ya hecha)
- Proyecto de Google Cloud: **Mis Lecturas** (`mis-lecturas-513121`).
- API habilitada: **Google Drive API** (no hace falta la Docs API: los documentos se crean y leen con Drive).
- Pantalla de consentimiento: Externa, en modo de prueba; usuario de prueba: el dueño de la cuenta.
- Permiso: `https://www.googleapis.com/auth/drive.file` (solo los archivos que crea la app).
- ID de cliente OAuth (Aplicación web) en `config.js`. Orígenes autorizados: `https://villanuevaramosjaime2018-bot.github.io` y `http://localhost:8000`.

Para rehacerla en otra cuenta: crea un proyecto, habilita la Drive API, configura la pantalla de consentimiento con el permiso `drive.file`, crea un ID de cliente «Aplicación web» con tus orígenes y pégalo en `config.js`.

## Decisiones técnicas
- **Voz:** Web Speech API de Chrome (es-PE): gratis, sin servidor y en tiempo real. En Android se dicta frase a frase para evitar texto duplicado.
- **Inicio de sesión:** Google Identity Services con el permiso mínimo `drive.file`.
- **Documentos:** Drive API v3 convierte HTML en Google Doc y lo exporta a texto o a Word.
- **Código:** HTML, CSS y JavaScript sin frameworks; PWA con service worker para abrirla sin conexión.

## Ideas para la versión 2
1. Etiquetas por capítulo o página dentro de cada sesión.
2. Búsqueda dentro de todos los resúmenes.
3. Resumen automático con IA de cada libro o sesión.
