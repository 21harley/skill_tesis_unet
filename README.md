# Skill: tesis-unet

Skill de **Agent Skills** (formato `SKILL.md`) con las normas del Trabajo de
Aplicación Profesional, modalidad Proyecto Especial de Grado, de la UNET.
Solo usa `name` y `description` en el frontmatter, así que es portable a
Claude Code, Codex, Gemini CLI, Cursor y otros agentes compatibles.

## Estructura

```
tesis-unet/                 ← la skill (esto es lo que se instala)
├── SKILL.md
└── references/
    ├── estructura.md       ← propuesta, proyecto y contenido de cada capítulo
    ├── formato.md          ← márgenes, fuente, títulos, tablas, figuras…
    ├── citas-referencias.md
    ├── plantillas.md       ← portada, resumen, cartas y actas
    └── aplicar-en-word.md  ← pasos en Word y lista de verificación
fuente/                     ← instructivo original (PDF y texto extraído)
```

## Instalar

### Claude Code y OpenCode (una sola instalación sirve para los dos)
OpenCode también lee `~/.claude/skills/`. Enlaza la carpeta una vez:

```powershell
New-Item -ItemType Junction -Path "$HOME\.claude\skills\tesis-unet" -Target "$PWD\tesis-unet"
```

Si prefieres la ruta neutra, `~/.agents/skills/tesis-unet` la leen OpenCode,
Codex y otros agentes. La carpeta debe llamarse igual que el campo `name`:
`tesis-unet`.

### Claude.ai (web o escritorio)
Comprime la carpeta `tesis-unet/` en un `.zip` y súbelo en
*Configuración → Capacidades → Skills*.

```powershell
Compress-Archive -Path tesis-unet -DestinationPath tesis-unet.zip -Force
```

### ChatGPT (GPT personalizado o Proyecto)
ChatGPT no carga carpetas de skills, así que se arma a mano:
1. **Instrucciones**: pega el contenido de `SKILL.md` sin el bloque `---` del inicio.
2. **Conocimiento o archivos**: sube todos los archivos de `references/`.

La skill ya está escrita para buscar esos archivos por nombre cuando no hay carpetas.

## Desinstalar

### Claude Code y OpenCode
Borra solo el enlace; tu carpeta `tesis-unet/` no se toca:

```powershell
cmd /c rmdir "$HOME\.claude\skills\tesis-unet"
```

Si la instalaste en la ruta neutra, borra también `"$HOME\.agents\skills\tesis-unet"`.

> No uses `Remove-Item -Recurse` sobre el enlace. En Windows PowerShell 5.1
> puede borrar el contenido real de la carpeta.

### Claude.ai
En *Configuración → Capacidades → Skills*, desactiva o elimina `tesis-unet`.

### ChatGPT
Borra el GPT personalizado o, en el Proyecto, quita las instrucciones y los
archivos de `references/`.

## Reglas para no romper la compatibilidad
- En el frontmatter, usa solo `name` y `description` (máximo 1024 caracteres).
- `name`: minúsculas, números y guiones, y debe coincidir con el nombre de la carpeta.
- Instrucciones neutras: nada de "usa la herramienta X" de un agente concreto.

## Pendiente
- [ ] Verificar las reglas marcadas como dudosas en `formato.md` (nivel 3 de títulos, inconsistencias) y en `plantillas.md` (porcentajes de evaluación).
- [ ] Añadir `assets/plantilla.docx` (con python-docx o la plantilla del departamento).
- [ ] Opcional: un script `scripts/revisar_docx.py` que compruebe márgenes, fuente e interlineado de un .docx.
- [ ] Probar con una tesis real.
