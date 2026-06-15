# Christian Albornoz

![header](header.svg)

Contador Auditor reconvertido en ingeniero de software. Trabajo en productos donde la arquitectura y el dominio contable tienen que convivir sin fricción: datos confiables, reglas de negocio explícitas y una interfaz que no esconda complejidad detrás de improvisación.

Este repositorio funciona como vitrina pública de mi trabajo. Los repositorios operativos del ecosistema son privados, así que aquí concentro una versión publicable de su contexto, sus decisiones arquitectónicas y el rol que cumple cada pieza.

## Ecosistema — Albornoz Accounting

El sistema contable multi-tenant. Tres capas con fronteras nítidas: Nostromo carga los datos, Orchestrator decide, Sevastopol muestra.

| Proyecto | Rol | Stack principal | Estado | Más info |
| :--- | :--- | :--- | :--- | :--- |
| **Nostromo** | Core de datos, ETL y automatización | `Python` · `PostgreSQL` · `Playwright` | 🔒 privado · beta `v0.1.0` en camino | [projects/nostromo.md](projects/nostromo.md) |
| **Orchestrator** | Backend de negocio, API y seguridad | `Node.js` · `TypeScript` · `Express` | 🔒 privado · beta `v0.1.0` en camino | [projects/orchestrator.md](projects/orchestrator.md) |
| **Sevastopol** | Frontend, BFF y experiencia de usuario | `Astro` · `SolidJS` · `Tailwind` | 🔒 privado · beta `v0.1.0` en camino | [projects/sevastopol.md](projects/sevastopol.md) |

## Herramientas y documentación

Documentación y tooling propio creados para sostener el ecosistema. Repos operativos privados; documentos públicos sanitizados.

- **[Jean d'Arc](https://docs.albornoz.studio/)** — 🌐 live — Documentación, arquitectura y dominio contable del ecosistema, con lado contable y lado dev en paralelo. Único proyecto público del ecosistema. `Astro Starlight` · `Mermaid` · [doc](projects/jean-d-arc.md)
- **[Cortex](https://marketplace.visualstudio.com/items?itemName=AlbornozStudio.cortex-local)** — 🟡 pre-alpha en Marketplace — Extensión de VS Code que visualiza el sistema (pipelines, planes en DAG/PERT, datos por tenant) y se integra con Claude Code. `TypeScript` · `MongoDB` · `React Flow` · [repo](https://github.com/ChrisTkm/nostromo_cortex)
- **ai-skills** — 🔒 privado — Hub canónico de skills de IA reutilizables: una sola fuente de verdad sincronizada hacia Claude Code, Codex y GitHub Copilot, global y por repo. `Node.js` · `Tooling`
- **[ai-voice](https://github.com/ChrisTkm/ai-voice)** — 🟢 `v0.1.0` — Capa local de notificaciones por voz: clips cortos por *intent* que traducen eventos de Claude Code, Codex y Copilot en señales auditivas. `PowerShell` · `Narakeet` _(C# inline para reproducción MP3 / fallback multimedia en Windows)_
- **[Signal](https://github.com/ChrisTkm/ai-signal)** — 🟡 prototipo — Extensión liviana de VS Code y servidor MCP read-only que convierte actividad técnica pública en contexto local para asistentes de IA. `Node.js` · `VS Code` · `MCP` · [doc](projects/ai-signal.md)

## Cómo navegar este portafolio

1. **Escaneo rápido** → las tablas de arriba.
2. **Resumen sanitizado por proyecto** → `projects/*.md`. Una página por componente con su propósito, arquitectura y límites públicos.
3. **Inmersión técnica completa** → [docs.albornoz.studio](https://docs.albornoz.studio/) (Jean d'Arc). Documenta a Orchestrator y Sevastopol con más profundidad que esta vitrina.

Si te interesa la arquitectura backend, empezá por [`orchestrator.md`](projects/orchestrator.md). Si te interesa el dominio contable, empezá por [`jean-d-arc.md`](projects/jean-d-arc.md) y de ahí al sitio.

## Qué problemas ataca este ecosistema

- Reducir trabajo manual en cargas contables, documentos tributarios y procesos repetitivos.
- Concentrar reglas de negocio, permisos y contexto multi-tenant en una capa verificable.
- Entregar una interfaz operable para tareas complejas sin exponer complejidad interna al navegador.
- Mantener documentación útil para onboarding, operación y evolución técnica aunque los repositorios no sean públicos.

## Principios de trabajo

- El dato contable no se improvisa: la trazabilidad y la validación son parte del diseño.
- El frontend no absorbe lógica de negocio que pertenece al backend.
- La documentación no es un accesorio; es parte del sistema.
- La automatización tiene que reducir errores operativos, no solo ahorrar clicks.

## Estado del sistema

Snapshot del ecosistema — cada componente con su etapa de release y el stack consolidado.

![System Status](assets/status_card.svg)

## Contacto

- **Email** — [chris@albornoz.studio](mailto:chris@albornoz.studio)
- **GitHub** — [github.com/ChrisTkm](https://github.com/ChrisTkm)
- **Documentación pública** — [docs.albornoz.studio](https://docs.albornoz.studio/)
- **Ubicación** — Santiago, Chile
