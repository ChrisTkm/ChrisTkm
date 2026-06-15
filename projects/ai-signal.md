# Signal

Contexto técnico local para asistentes de IA, desde actividad pública curada.

> [!NOTE]
> Este documento resume el proyecto público sin incluir configuración local, caches generados ni detalles privados de uso.

[![VS Code](https://img.shields.io/badge/Surface-VS%20Code-007acc?style=flat-square&logo=visualstudiocode&logoColor=white)](https://code.visualstudio.com/)
[![MCP](https://img.shields.io/badge/Protocol-MCP-a78bfa?style=flat-square)](#)
[![Node.js](https://img.shields.io/badge/Runtime-Node.js-34d399?style=flat-square&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Status](https://img.shields.io/badge/Status-Prototype-f2ce7e?style=flat-square)](#)

## Qué resuelve

Signal es una extensión liviana de VS Code y un colector local para actividad técnica pública. Toma historias de Hacker News, las normaliza, las agrupa con una taxonomía personal y guarda un cache pequeño para que el contexto reciente esté disponible sin depender de un servicio externo.

Su objetivo no es razonar por la IA. Su rol es preparar señales limpias para que asistentes como Codex, Claude, OpenCode u otros clientes MCP puedan leer contexto útil cuando corresponde.

## Forma actual

- Entrada en la status bar de VS Code.
- Panel compacto con lista rankeada, detalle seleccionado, link al artículo y comentarios de Hacker News.
- Colector local para historias de Hacker News.
- Ranking por actividad, edad, pesos de feeds, keywords y dominios.
- Cache persistente bajo `.ai-signal/`.
- Servidor MCP stdio, read-only, sobre el mismo cache local.

## Feed groups

Signal usa feeds opinados en vez de categorías genéricas:

- `Cargo Bay`: AstroJS, NodeJS, ReactJS, TypeScript.
- `Cortex Feed`: GitHub Copilot, Python, MCP, OpenCode, Perplexity, Cursor, Claude, Cloudflare, agentic AI.
- `Deep Space Relay`: GitKraken, KeePass, Brave, Codex, VS Code.
- `Nostromo Finance`: PostgreSQL, SQL Server, Docker, MariaDB, MongoDB.

La configuración vive en `config/feeds.sample.json`. El matching es intencionalmente estricto: si una historia no calza con keywords o dominios configurados, no entra al feed.

## MCP

El servidor MCP expone herramientas de lectura sobre el cache local:

- `signal_get_top`
- `signal_search`
- `signal_get_digest`
- `signal_get_item`
- `signal_get_groups`

El servidor no fetchea durante una request. Lee el estado local ya recolectado y lo entrega como contexto estructurado.

## Límites públicos

Por diseño, este resumen no publica:

- caches locales generados;
- configuraciones personales privadas;
- señales históricas específicas de uso;
- credenciales o integración con servicios externos.

## Estado público del proyecto

Signal está en etapa de prototipo funcional. La extensión VS Code, el colector de Hacker News y el servidor MCP read-only ya existen. El siguiente borde natural es ampliar fuentes, editar feeds desde la UI y estabilizar el packaging cuando la superficie del producto esté lista.
