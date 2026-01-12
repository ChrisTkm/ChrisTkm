![Orchestrator Banner](assets/orchestrator/banner.svg)

# ⚙️ Orchestrator Backend

**"La Fuente de Verdad" del Ecosistema Contable.**

> [!NOTE]
> Este proyecto es **Privado**. Esta página es una vitrina de su arquitectura y propósito.

[![Node.js](https://img.shields.io/badge/Runtime-Node.js%2020+-339933?style=flat-square&logo=node.js&logoColor=white)](https://nodejs.org/)
[![TypeScript](https://img.shields.io/badge/Lang-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Express](https://img.shields.io/badge/Framework-Express%205-000000?style=flat-square&logo=express&logoColor=white)](https://expressjs.com/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

---

**Orchestrator** es el núcleo backend del Ecosistema Contable, responsable de toda la **lógica de negocio**, **validación**, **seguridad** y **persistencia de datos**.

Actúa como el "árbitro central" que protege la integridad de los datos y asegura que el Frontend (Sevastopol) solo se preocupe de la UI.

## 🤖 Agente Orchestrator

> *"Arquitectura Backend, Seguridad y Lógica de Negocio"*

Este repositorio es vigilado por el **Agente Orchestrator**, encargado de mantener la integridad arquitectónica del backend.

**Responsabilidades:**

- **Arquitecto Backend**: Estructura sobre velocidad, lógica de negocio encapsulada.
- **Auditor de Seguridad**: Validación de inputs, RBAC, protección de endpoints.
- **Ejecutor de Pruebas**: Tests E2E y unitarios para flujos críticos.

---

## 🏗️ Arquitectura: Hybrid Core

El backend implementa una arquitectura **Pragmatic Hybrid 2025**:

| Dominio | Responsabilidad | Ubicación |
|---------|-----------------|-----------|
| **Writes & Logic** | Cálculos complejos (nóminas, impuestos), validaciones | TypeScript (Services) |
| **Reads & Reports** | Listados masivos, dashboards | PostgreSQL (Smart Views) |

### Flujo de Datos

```
Sevastopol → /api/* → Orchestrator → PostgreSQL (Multi-Tenant)
                ↓
        Auth Middleware → RBAC → Service Layer → Repository → DB
```

## 🛠️ Stack Tecnológico

| Capa | Tecnología | Uso |
|------|------------|-----|
| **Runtime** | [Node.js 20+](https://nodejs.org/) | Motor de ejecución |
| **Framework** | [Express 5.x](https://expressjs.com/) | HTTP Server y Routing |
| **Lenguaje** | [TypeScript](https://www.typescriptlang.org/) | Tipado estricto |
| **Base de Datos** | [PostgreSQL](https://www.postgresql.org/) | Multi-tenant via Pools |
| **Auth** | JWT + Session Cookies | Seguridad basada en `sid` |
| **Validación** | [express-validator](https://express-validator.github.io/) | Sanitización de inputs |
| **Testing** | [Jest](https://jestjs.io/) + [Supertest](https://github.com/ladjs/supertest) | Unit y E2E |

## 📂 Estructura del Proyecto

```text
src/
├── app.ts                    # Express app factory
├── server.ts                 # HTTP server bootstrap
├── lib/
│   ├── db.ts                 # Pool management (central, common, tenant)
│   ├── rbac.ts               # Role-Based Access Control
│   └── tenantResolver.ts     # Tenant context resolution
├── middleware/
│   └── auth.ts               # authenticateToken + authorizeRoute
├── domain/                   # Business Logic Layer
│   ├── auth/                 # Authentication services
│   ├── command/              # Tenant & User management
│   └── remuneraciones/       # Payroll domain
└── routes/
    ├── command/              # nostromo_command (Admin)
    ├── common/               # nostromo_common (Params)
    ├── operations/           # operaciones_sii (Sales)
    └── remuneraciones/       # Payroll endpoints
```

## 🔐 Seguridad

- **Autenticación**: Session-based JWT en cookie `httpOnly` (`sid`)
- **Autorización**: RBAC con roles `SUPER_ADMIN`, `ADMIN`, `USER`
- **Validación**: Todos los inputs validados con express-validator
- **Headers**: Helmet para protección de headers HTTP
- **Rate Limiting**: Límites por rol de usuario

---

<div align="center">
  <sub>Parte del ecosistema <b>Albornoz Accounting System</b>.</sub>
</div>
