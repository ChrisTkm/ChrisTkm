![Orchestrator Banner](assets/orchestrator/banner.svg)

# Orchestrator

Backend de negocio, API y seguridad del ecosistema contable.

> [!NOTE]
> Este documento es público y sanitizado. Describe el enfoque arquitectónico y las responsabilidades del backend sin exponer endpoints internos sensibles, credenciales ni detalles operativos reservados.

[![Node.js](https://img.shields.io/badge/Runtime-Node.js%2020+-339933?style=flat-square&logo=node.js&logoColor=white)](https://nodejs.org/)
[![TypeScript](https://img.shields.io/badge/Lang-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Express](https://img.shields.io/badge/Framework-Express%205-000000?style=flat-square&logo=express&logoColor=white)](https://expressjs.com/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

## Qué resuelve

Orchestrator concentra la lógica de negocio que no debe quedar dispersa entre pantallas, scripts o decisiones ad hoc. Es la capa que valida, autoriza, compone reglas y protege la consistencia transaccional del sistema.

Su rol es sencillo de definir y difícil de reemplazar: actuar como fuente de verdad operacional.

## Responsabilidades

- Exponer API para el frontend y otros consumidores controlados.
- Validar entradas antes de que toquen la lógica de negocio.
- Resolver contexto de tenant y permisos de usuario.
- Encapsular reglas de negocio y cálculos críticos.
- Coordinar persistencia, lectura y escritura hacia PostgreSQL.
- Proveer una base comprobable mediante pruebas y convenciones claras.

## Modelo arquitectónico

El backend sigue una estrategia híbrida:

- la lógica y las escrituras viven en servicios TypeScript;
- las lecturas pesadas y reportes pueden apoyarse en SQL y vistas optimizadas;
- la seguridad y el contexto de acceso atraviesan el request desde el borde.

```text
Cliente / Frontend
   -> middleware de autenticación
   -> autorización por rol
   -> validación de input
   -> servicio de dominio
   -> repositorio / acceso a datos
   -> PostgreSQL
```

## Flujo operativo representativo

Un caso típico es el de una persona usuaria autenticada que necesita operar sobre información de un tenant específico. Orchestrator resuelve el contexto, verifica permisos, valida el input, aplica reglas de negocio y recién después persiste o devuelve una respuesta consistente al frontend.

## Capas principales

- borde HTTP para recibir requests y aplicar middleware transversal;
- autenticación y autorización para identidad, roles y contexto de acceso;
- servicios de dominio donde viven reglas, validaciones y coordinación;
- persistencia y lectura optimizada detrás de una capa explícita.

Aunque la estructura interna evolucione, la frontera conceptual se mantiene: HTTP en el borde, negocio en el dominio y datos detrás de contratos claros.

## Seguridad

La seguridad no es una capa decorativa. Forma parte del flujo normal del backend:

- autenticación basada en sesión o token;
- autorización con roles y rutas protegidas;
- validación y sanitización de inputs;
- hardening HTTP;
- separación de contexto por tenant.

## Principios de implementación

- El frontend no decide reglas contables.
- Los cálculos críticos no se duplican en múltiples capas.
- Los errores deben ser trazables y operar con contratos consistentes.
- La estructura del código debe favorecer mantenimiento antes que velocidad aparente.

## Testing y confiabilidad

Orchestrator está pensado para sostener pruebas en más de un nivel:

- unitarias para servicios y utilidades;
- integración para rutas y persistencia;
- end-to-end para flujos críticos expuestos al usuario.

No todo se publica aquí, pero el criterio es claro: la capa central del negocio debe ser verificable.

## Límites públicos

Esta página omite deliberadamente:

- nombres reales de tenants o clientes;
- contratos internos completos de API;
- configuración de secretos, sesiones o despliegue;
- detalles finos de rate limiting, observabilidad o infraestructura.

## Relación con otros proyectos

- `Sevastopol` consume esta capa a través de un BFF y rutas controladas.
- `Nostromo` complementa el backend con procesos batch y trabajo de datos.
- `Jean d'Arc` concentra la documentación y las convenciones que sostienen el sistema.

## Estado público del proyecto

Orchestrator representa la disciplina del sistema: una capa intermedia que permite crecer sin volver caótico el dominio contable ni filtrar lógica sensible hacia la interfaz.
