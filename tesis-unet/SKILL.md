---
name: tesis-unet
description: Normas de formato y estructura del Trabajo de Aplicación Profesional (TAP), modalidad Proyecto Especial de Grado (PEG), de la UNET (Universidad Nacional Experimental del Táchira). Úsala cuando el usuario redacte, revise, estructure o formatee una propuesta o un proyecto/tesis/trabajo de grado de la UNET, o pregunte por márgenes, fuente, interlineado, títulos, portada, resumen, índice, tablas, figuras, citas, referencias, anexos o cartas según las normas UNET.
---

# Tesis UNET (TAP – Proyecto Especial de Grado)

Fuente única: *Instructivo para la elaboración del Trabajo de Aplicación
Profesional en la modalidad Proyecto Especial de Grado*, UNET, Decanato de
Docencia, mayo 2012.

## Reglas de uso

1. Antes de responder, lee el archivo que corresponda. Están en `references/`
   o, si no hay carpetas (por ejemplo en ChatGPT), entre los archivos adjuntos
   o de conocimiento con el mismo nombre:
   - `estructura.md`: qué lleva la propuesta y el proyecto, y qué va en cada capítulo.
   - `formato.md`: página, márgenes, fuente, interlineado, paginación, niveles de títulos, tablas, figuras, anexos, ecuaciones y redacción.
   - `citas-referencias.md`: citas textuales y parafraseadas, y cómo escribir cada tipo de referencia.
   - `plantillas.md`: portada, contraportada, resumen, cartas y actas.
   - `aplicar-en-word.md`: pasos en Word para aplicar el formato a mano.
2. No inventes reglas. Si algo no está en `references/`, dilo y sugiere
   consultarlo con el tutor o la Comisión TAP del departamento.
3. El instructivo es de 2012 y su estilo de referencias es propio (basado en
   UPEL/APA de esa época), **no APA 7**. Si el usuario pide APA 7, avísale
   de la diferencia y pregúntale cuál exige su departamento.
4. Responde en español.

## Adapta el trabajo a tu entorno

Antes de una tarea con documentos, identifica qué puedes hacer en tu entorno.
No supongas capacidades que no tienes.

### A. Terminal o agente con archivos (Claude Code, OpenCode, Codex, etc.)
Puedes leer y escribir archivos y ejecutar comandos.
- **Revisar un .docx**: ábrelo y mide el formato real; no lo deduzcas.
  Usa `python-docx` si está instalado; si no, descomprime el `.docx` y lee
  `word/document.xml`. Valores de referencia en Word (1 cm = 567 twips):
  - Márgenes: `w:pgMar` con `left="2268"` (4 cm) y `right`, `top` y `bottom` en `"1701"` (3 cm).
  - Papel carta: `w:pgSz` con `w:w="12240"` y `w:h="15840"`.
  - Fuente: Times New Roman, `w:sz="24"` (12 pt; el valor va en medios puntos).
  - Interlineado 1,5: `w:spacing w:line="360" w:lineRule="auto"`. Sencillo: `line="240"`.
  - Revisa también los estilos (`word/styles.xml`), no solo los párrafos sueltos.
- **Generar contenido**: escribe archivos (`.md`, o `.docx` si hay
  `python-docx`) en la carpeta del usuario y dile la ruta. No sobrescribas su
  tesis sin preguntar; crea una copia.
- **PDF**: puedes extraer el texto para revisar estructura y citas, pero el
  formato de un PDF no es fiable. Pide el `.docx` para revisar formato.

### B. Chat (ChatGPT, Claude.ai, Gemini, etc.)
- **Texto pegado**: el texto pegado **no conserva** márgenes, fuente,
  interlineado ni numeración. Revisa solo **estructura, redacción, citas y
  referencias**, y dilo explícitamente. Para el formato, entrega la lista de
  verificación de `aplicar-en-word.md`.
- **Archivo subido**: si tienes un entorno para ejecutar código, procede
  como en el caso A. Si solo ves el texto del archivo, trátalo como texto pegado.
- **Generar contenido**: entrégalo en el chat, listo para copiar: portada,
  cartas, índice y referencias en bloques de texto. Indica el formato que
  debe aplicarse en Word con los pasos de `aplicar-en-word.md`. Si puedes
  generar archivos descargables, ofrece también el `.docx`.
- **Documentos largos**: si la tesis no cabe completa, pide que la envíe
  por capítulos y revisa uno por vez.

En ambos casos, dile al usuario qué pudiste comprobar y qué no.

## Tareas típicas

### Revisar un documento
1. Compara el documento con `estructura.md` (secciones y orden) y con `formato.md`.
2. Devuelve una lista con este formato: **ubicación → problema → regla (archivo/sección) → corrección**.
3. Agrupa por gravedad: primero estructura faltante, luego formato, luego estilo.

### Armar el esqueleto de la tesis
1. Pregunta si es **propuesta** o **proyecto final**, y si tiene capítulo VI (Propuesta).
2. Genera el índice según `estructura.md` y elige el caso de niveles de títulos de `formato.md`.

### Formatear citas o referencias
Identifica el tipo de fuente y aplica la plantilla exacta de `citas-referencias.md`.

### Generar portada, resumen o cartas
Usa `plantillas.md` y rellena con los datos del usuario. Pide los que falten
(departamento, carrera, título, autores, cédulas, tutor, ciudad y fecha).
