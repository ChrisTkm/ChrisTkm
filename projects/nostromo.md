![Nostromo Banner](assets/nostromo/banner.svg)

# Nostromo

Core de datos, automatización y procesamiento batch del ecosistema contable.

> [!NOTE]
> Este documento es una versión pública y sanitizada del proyecto. Resume la arquitectura y el propósito del sistema sin exponer credenciales, esquemas internos completos ni detalles operativos sensibles.

[![Python](https://img.shields.io/badge/Python-3.11+-3776ab?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-4169e1?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Data Engineering](https://img.shields.io/badge/Focus-Data%20Engineering-orange?style=flat-square)](#)

## Qué resuelve

Nostromo existe para absorber el trabajo pesado del sistema contable: ingesta de datos, normalización, procesos programados, estructura de base de datos y automatizaciones que no deberían depender de la interfaz ni del backend transaccional.

Dentro del ecosistema, su responsabilidad es preparar y custodiar información para que otras capas trabajen sobre una base consistente.

## Rol en la arquitectura

Mientras `Orchestrator` concentra la lógica online y `Sevastopol` la experiencia de usuario, Nostromo opera como plano de fondo:

- ejecuta pipelines ETL;
- procesa cargas masivas desde fuentes externas;
- organiza utilidades técnicas y scripts de mantenimiento;
- sostiene flujos que requieren trazabilidad y repetibilidad;
- sirve como punto natural para tareas de soporte de datos y operación.

## Capacidades principales

- Carga y transformación de documentos tributarios y archivos contables.
- Automatización de procesos periódicos y tareas operativas.
- Soporte para estructuras multi-tenant sobre PostgreSQL.
- Scripts de apoyo para mantenimiento, depuración y labores internas.
- Organización de conocimiento técnico y tooling asociado al ecosistema.

## Vista de arquitectura

```text
Fuentes externas
   -> validación y parsing
   -> normalización
   -> carga controlada
   -> persistencia / utilidades de soporte
   -> consumo por backend y operación interna
```

Este proyecto no compite con el backend HTTP. Su valor está en la robustez del procesamiento, no en servir vistas o endpoints.

## Áreas del proyecto

```text
accounting_system/   motores ETL y loaders especializados
db/                  utilidades SQL, apoyo de desarrollo y material histórico
auth/                conectividad y helpers de acceso
scripts/             automatización operativa
skills/              conocimiento y soporte para agentes/herramientas
docs/                documentación técnica interna
utils/               helpers compartidos
assets/              recursos gráficos y utilitarios
```

## Flujos típicos

### Ingesta contable

1. Un origen externo entrega archivos o registros.
2. Nostromo valida formato y consistencia básica.
3. El dato se normaliza para hacerlo utilizable aguas abajo.
4. El resultado se persiste o se deja listo para consumo del backend.

### Operación y mantenimiento

1. Un proceso interno necesita revisión o apoyo técnico.
2. Nostromo ejecuta scripts o tareas programadas.
3. El sistema deja trazas, resultados o artefactos reproducibles.

## Decisiones de diseño

- Python como lenguaje principal para procesos ETL y automatización.
- PostgreSQL como soporte natural para integridad y trazabilidad de datos.
- Separación entre procesamiento batch y lógica de negocio online.
- Herramientas y scripts versionados para reducir trabajo manual repetitivo.

## Límites públicos

Por seguridad y privacidad, esta página no publica:

- credenciales o variables de entorno;
- esquemas productivos completos;
- estructura exacta de tenants y clientes;
- detalles de despliegue, jobs programados o topología interna;
- contratos sensibles con integraciones externas.

## Relación con el resto del ecosistema

- `Orchestrator` consume y gobierna negocio sobre datos ya estructurados.
- `Sevastopol` nunca se conecta directamente a esta capa.
- `Jean d'Arc` documenta decisiones, procesos y convenciones relacionadas.

## Estado público del proyecto

Nostromo representa la parte menos visible del sistema, pero también una de las más críticas. Su valor no está en la UI, sino en la confiabilidad con que transforma procesos contables complejos en flujos repetibles y auditables.
