![Nostromo Banner](assets/nostromo/banner.svg)

# 🚀 Nostromo Core

**"El Corazón Operativo" del Ecosistema Contable.**

> [!NOTE]
> Este proyecto es **Privado**. Esta página es una vitrina de su arquitectura y propósito.

[![Python](https://img.shields.io/badge/Python-3.11+-3776ab?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-4169e1?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Agent](https://img.shields.io/badge/Agent-Nostromo-orange?style=flat-square&logo=robot)](#)

---

**Nostromo** es el backend fundacional y núcleo de procesamiento del **Albornoz Accounting System**.

A diferencia del **Orchestrator** (Node.js) que maneja la lógica de negocio online, Nostromo se especializa en el trabajo pesado: **procesamiento batch, ETLs masivos, gestión estructural de base de datos y memoria corporativa**.

## 🤖 Agente Nostromo

> *"Guardián Multi-Tenant, Ingeniero de Datos & Core System"*

Este repositorio es el dominio del **Agente Nostromo**, una inteligencia especializada encargada de la integridad de datos, procesos de fondo y la estructura de conocimiento.

**Responsabilidades:**

- **🛡️ Guardián de Datos**: Administra y protege la estructura de la base de datos PostgreSQL (`db/`), gestionando migraciones y esquemas multi-tenant.
- **🔄 ETL Operator**: Ejecuta pipelines de extracción y carga de datos masivos (SII, Previred, Bancos) a través del `accounting_system`.
- **🧠 Knowledge Base Manager**: Mantiene la **Matriz de Habilidades** y las **Instrucciones del Agente**.
- **🛠️ Tooling & Scripts**: Provee utilidades avanzadas y scripts de mantenimiento.

---

## 📂 Estructura del Proyecto

```text
Nostromo/
├── accounting_system/      # ⚙️ Motores ETL y Loaders (SII, Previred)
├── db/                     # 🗄️ Definiciones de Base de Datos (PostgreSQL)
│   ├── legacy_v1/          # 📜 Archivos históricos y templates antiguos
│   ├── playground/         # 🧪 Scripts de prueba y experimentación
│   └── helpers/            # 🛠️ Scripts SQL de utilidad
├── skills/                 # 🧠 Matriz de Conocimiento y Habilidades de Agentes
├── auth/                   # 🔐 Conectores de Base de Datos y Utilidades de Conexión
├── scripts/                # 📜 Scripts de Mantenimiento y Automatización
├── docs/                   # 📘 Documentación Técnica Profunda
├── arkana/                 # 🧪 Laboratorio y Herramientas Experimentales
├── utils/                  # 🛠️ Utilidades compartidas y Helpers
└── assets/                 # 🎨 Recursos Gráficos y Herramientas (Antigravity)
```

## ⚙️ Componentes Principales

### 1. Accounting System (ETL)

El motor de ingesta de datos. Contiene scripts Python especializados para:

- **SII Loader**: Carga masiva y procesamiento de documentos tributarios (RCV).
- **Previred**: Procesamiento automatizado de planillas de cotizaciones.
- **Banco Central**: Obtención y normalización de indicadores económicos.

### 2. Database (DB)

**Fuente de Verdad Externa**: Los esquemas productivos ("Modernos") se mantienen en el repositorio hermano `Accounting/mother` (carpeta `accounting_template`).
Nostromo actúa como el **motor de ejecución** y orquestación para estos esquemas.

La carpeta `db/` interna de este repositorio contiene herramientas de desarrollo (`playground`), scripts de utilidad (`helpers`) y archivos históricos (`legacy_v1`).

### 3. Skill Matrix

El centro de conocimiento compartido. Aquí se definen las capacidades de cada agente (**Jean d'Arc**, **Sevastopol**, **Orchestrator**) y se documenta cómo deben interactuar entre sí.

---

## 🔐 Seguridad

Nostromo opera como un componente crítico de infraestructura.

- **Credenciales**: Gestionadas vía variables de entorno (`.env`) y `EmpresaConfigManager`.
- **Accesos**: Limitados a roles de administración y servicios backend.
- **Logging**: Trazabilidad completa en `logs/`.

---

<div align="center">
  <sub>Parte del ecosistema <b>Albornoz Accounting System</b>.</sub>
</div>
