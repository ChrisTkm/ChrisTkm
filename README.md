# Christian Albornoz

![header](header.svg)

Contador Auditor reconvertido en ingeniero de software. Trabajo en productos donde la arquitectura y el dominio contable tienen que convivir sin fricción: datos confiables, reglas de negocio explícitas y una interfaz que no esconda complejidad detrás de improvisación.

Este repositorio funciona como vitrina pública de mi trabajo. Los repositorios operativos del ecosistema son privados, así que aquí concentro una versión publicable de su contexto, sus decisiones arquitectónicas y el rol que cumple cada pieza.

## Ecosistema

| Proyecto | Rol | Stack principal | Visibilidad | Más info |
| :--- | :--- | :--- | :--- | :--- |
| **Nostromo** | Core de datos, ETL y automatización | `Python` `PostgreSQL` `Data Engineering` | 🔒 privado | [projects/nostromo.md](projects/nostromo.md) |
| **Orchestrator** | Backend de negocio, API y seguridad | `Node.js` `Express` `TypeScript` | 🔒 privado | [projects/orchestrator.md](projects/orchestrator.md) |
| **Sevastopol** | Frontend, BFF y experiencia de usuario | `Astro` `SolidJS` `Tailwind` | 🔒 privado | [projects/sevastopol.md](projects/sevastopol.md) |
| **Jean d'Arc** | Documentación, arquitectura y dominio contable | `Astro Starlight` `Mermaid` | 🌐 [docs.albornoz.studio](https://docs.albornoz.studio/) | [projects/jean-d-arc.md](projects/jean-d-arc.md) |

## Cómo navegar este portafolio

1. **Escaneo rápido** → la tabla de arriba.
2. **Resumen sanitizado por proyecto** → `projects/*.md`. Una página por componente con su propósito, arquitectura y límites públicos.
3. **Inmersión técnica completa** → [docs.albornoz.studio](https://docs.albornoz.studio/) (Jean d'Arc). Es el único proyecto público del ecosistema y documenta a Orchestrator y Sevastopol con más profundidad que esta vitrina.

Si te interesa la arquitectura backend, empezá por [`orchestrator.md`](projects/orchestrator.md). Si te interesa el dominio contable, empezá por [`jean-d-arc.md`](projects/jean-d-arc.md) y de ahí al sitio.

## Herramientas y extensiones

Tooling propio creado para sostener el ecosistema. Repositorios operativos privados, documentos públicos sanitizados.

- **[Cortex](https://github.com/ChrisTkm/nostromo_cortex)** — Extensión VS Code para visualización de planes de trabajo y notas técnicas en grafos PERT/DAG. `TypeScript` · `MongoDB` · `React Flow`
- **[ai-voice](https://github.com/ChrisTkm/ai-voice)** — Librería local de notificaciones por voz integrada al flujo de desarrollo. `PowerShell` · `C#` · `Narakeet`

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

Snapshot del estado público del ecosistema — proyectos activos, stack consolidado y métricas agregadas.

![System Status](assets/status_card.svg)

## Contacto

- **Email** — [chris@albornoz.studio](mailto:chris@albornoz.studio)
- **GitHub** — [github.com/ChrisTkm](https://github.com/ChrisTkm)
- **Documentación pública** — [docs.albornoz.studio](https://docs.albornoz.studio/)
- **Ubicación** — Santiago, Chile
