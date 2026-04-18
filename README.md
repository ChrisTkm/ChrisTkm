# Christian Albornoz

![header](header.svg)

Contador Auditor reconvertido en ingeniero de software. Trabajo en productos donde la arquitectura y el dominio contable tienen que convivir sin fricción: datos confiables, reglas de negocio explícitas y una interfaz que no esconda complejidad detrás de improvisación.

Este repositorio funciona como vitrina pública de mi trabajo. Los repositorios operativos del ecosistema son privados, así que aquí concentro una versión publicable de su contexto, sus decisiones arquitectónicas y el rol que cumple cada pieza.

## Ecosistema

| Proyecto | Rol | Stack principal | Documento público |
| :--- | :--- | :--- | :--- |
| **Nostromo** | Core de datos, ETL y automatización | `Python` `PostgreSQL` `Data Engineering` | [projects/nostromo.md](projects/nostromo.md) |
| **Orchestrator** | Backend de negocio, API y seguridad | `Node.js` `Express` `TypeScript` | [projects/orchestrator.md](projects/orchestrator.md) |
| **Sevastopol** | Frontend, BFF y experiencia de usuario | `Astro` `SolidJS` `Tailwind` | [projects/sevastopol.md](projects/sevastopol.md) |
| **Jean d'Arc** | Documentación, arquitectura y guías operativas | `Astro Starlight` `Mermaid` | [projects/jean-d-arc.md](projects/jean-d-arc.md) |

## Herramientas y extensiones

Tooling propio creado para sostener el ecosistema. Repositorios operativos privados, documentos públicos sanitizados.

| Herramienta | Tipo | Stack principal | Documento público |
| :--- | :--- | :--- | :--- |
| **Cortex** | Extensión VS Code | `TypeScript` `MongoDB` `React Flow` | [github.com/ChrisTkm/nostromo_cortex](https://github.com/ChrisTkm/nostromo_cortex) |

## Qué encontrarás aquí

- Un resumen público por proyecto con su propósito, límites y arquitectura.
- Explicaciones suficientes para entender cómo se integran entre sí.
- Información sanitizada: sin credenciales, sin esquemas sensibles, sin endpoints internos ni detalles de despliegue reservados.

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

## Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Astro](https://img.shields.io/badge/Astro-BC52EE?style=flat-square&logo=astro&logoColor=white)
![SolidJS](https://img.shields.io/badge/SolidJS-2C4F7C?style=flat-square&logo=solid&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Estado del sistema

![System Status](assets/status_card.svg)

## Contacto

- Email: [chris@albornoz.studio](mailto:chris@albornoz.studio)
- Ubicación: Santiago, Chile
