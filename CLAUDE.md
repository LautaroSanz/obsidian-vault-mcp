# Obsidian Vault MCP Server

## Qué es

MCP server en TypeScript que expone herramientas para gestionar vaults de Obsidian desde Claude Code. Permite crear, leer, buscar, actualizar y agregar contenido a notas.

## Setup

```bash
npm install
npm run build
node dist/index.js
```

Registrar en la config de Claude Code apuntando a `dist/index.js` como MCP server stdio.

## Configuración de vaults

Editar `src/config.ts` para configurar:
- `VAULTS`: Record con nombre, path en disco, y flag de git
- `SUBJECT_TAGS`: Mapeo de nombres de materia/tema a slugs para tags

Las rutas son absolutas desde el home del usuario. Al clonar en otra máquina, actualizar los paths.

## Tools disponibles

- `create_note` — Crea nota con templates estructurados
- `read_note` — Lee contenido de una nota
- `search_notes` — Busca en la vault con grep
- `append_to_note` — Agrega contenido a una nota (puede apuntar a sección específica)
- `update_note` — Reescribe completamente una nota
- `list_subjects` — Lista la estructura de carpetas/materias de una vault

## Stack

- TypeScript, MCP SDK (`@modelcontextprotocol/sdk`), Zod
- Build: `tsc` directo
