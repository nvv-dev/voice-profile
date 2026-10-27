# voice-profile

> Que lo escrito por el agente suene a ti y no al modelo.

**Perfil de voz** · Skill para agentes de código de la comunidad [nvvdev](https://github.com/nvv-dev). Funciona en Claude Code como plugin o como skill suelta, y en cualquier agente compatible con el formato abierto [`SKILL.md`](https://agentskills.io).

*English summary at the end.*

## Qué hace

Con una entrevista corta y 3 a 5 textos reales que escribiste tú, arma dos archivos: `about-me.md` (quién eres, tu historia en hechos, tus opiniones y temas) y `voice.md` (cómo escribes: ritmo, vocabulario, estructura, postura y formato, con un ejemplo real para cada regla). No arranca sola al cargarse: primero pregunta si quieres hacer la entrevista.

## Objetivo

Darle a los agentes de copy y contenido una referencia concreta de tu voz, basada en evidencia y no en adjetivos.

## Cuándo usarla

- Antes de pedirle a un agente posts, correos o copy con tu voz
- Cuando el contenido generado suena genérico

## Cuándo no

- Si no tienes textos propios: escribe primero algunos sin ayuda
- Para imitar la voz de otra persona sin su permiso

## Ejemplo

```text
/voice-profile para mi marca personal; tengo tres posts de LinkedIn y un correo a clientes.
```

## Cómo se activa

Esta skill **solo se activa a mano** (`disable-model-invocation: true`): no ocupa contexto en cada sesión y la invocas cuando la necesitas:

- Instalada como plugin: `/voice-profile:voice-profile`
- Copiada a `.claude/skills/`: `/voice-profile`

## Instalación

### Opción 1: Claude Code, como plugin (recomendada)

Dentro de Claude Code:

```text
/plugin marketplace add nvv-dev/claude-plugins
/plugin install voice-profile@nvvdev
```

La primera línea agrega el catálogo de nvvdev una sola vez; la segunda instala esta skill. Si prefieres el paquete completo, instala `growth-workflow@nvvdev` en su lugar (incluye esta skill y las demás de [growth-workflow](https://github.com/nvv-dev/growth-workflow)); no instales los dos a la vez.

### Opción 2: Claude Code, copiando la skill

Para un solo proyecto (se comparte con tu equipo por git):

```bash
git clone --depth 1 https://github.com/nvv-dev/voice-profile.git /tmp/voice-profile
mkdir -p .claude/skills
cp -R /tmp/voice-profile/skills/voice-profile .claude/skills/
```

Para todos tus proyectos, cópiala en `~/.claude/skills/` en lugar de `.claude/skills/`.

### Opción 3: otros agentes

Copia la carpeta `skills/voice-profile/` en la carpeta de skills de tu agente (cada agente documenta la suya). Con la CLI [skills](https://github.com/vercel-labs/skills) de Vercel Labs:

```bash
DISABLE_TELEMETRY=1 npx skills add nvv-dev/voice-profile
```

### Verificar

Abre una sesión nueva y pregunta "¿qué skills tienes disponibles?"; `voice-profile` debe aparecer. Con el plugin, `/plugin` la muestra como instalada.

### Actualizar o desinstalar

- Plugin: `/plugin marketplace update nvvdev` para actualizar; `/plugin uninstall voice-profile@nvvdev` para quitarla.
- Copia manual: repite la copia para actualizar, o borra la carpeta `.claude/skills/voice-profile`.

Antes de instalar cualquier skill, incluida esta, conviene leerla: es un solo archivo, [`skills/voice-profile/SKILL.md`](skills/voice-profile/SKILL.md). Ver [vetting-external-skills](https://github.com/nvv-dev/vetting-external-skills).

## Contenido

| Ruta | Qué es |
|---|---|
| `skills/voice-profile/SKILL.md` | La skill: instrucciones en inglés para que los escáneres de seguridad las analicen completas; el agente responde en tu idioma |
| `.claude-plugin/plugin.json` | Manifiesto para instalarla como plugin |
| `.github/workflows/` | Validación de estructura y escaneo con SkillSpector en cada cambio |

## Contribuir

Este repo se **genera** desde [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow), donde vive la versión canónica. Abre issues y PRs allí. La mejor contribución es un caso real en la sección *Known failures* de la skill, con la regla que lo evita.

## Origen

Escrita desde cero por nvvdev. Inspirada en: [charlie947/social-media-skills](https://github.com/charlie947/social-media-skills) (voice-builder: interview plus real writing samples).

## Licencia

MIT.

---

## English

**voice-profile** — Builds about-me.md and voice.md from a short interview and three to five real texts; asks before starting.

Install in Claude Code with `/plugin marketplace add nvv-dev/claude-plugins` and `/plugin install voice-profile@nvvdev`, or copy `skills/voice-profile/` into `.claude/skills/` (project) or `~/.claude/skills/` (personal). Other agents: copy the folder into their skills directory, or run `DISABLE_TELEMETRY=1 npx skills add nvv-dev/voice-profile`. Manual-only skill: invoke it with `/voice-profile:voice-profile` (plugin) or `/voice-profile` (copied). Canonical source: [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow). License: MIT.
