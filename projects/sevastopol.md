![Sevastopol Banner](assets/sevastopol/banner.svg)

# Sevastopol

Frontend, BFF y capa de experiencia del ecosistema contable.

> [!NOTE]
> Esta es una descripción pública del proyecto. Resume arquitectura, principios y responsabilidades sin exponer código privado, credenciales ni detalles internos del producto.

[![Built with Astro](https://img.shields.io/badge/Built%20with-Astro-BC52EE?logo=astro&logoColor=white)](https://astro.build)
[![SolidJS](https://img.shields.io/badge/UI-SolidJS-446b9e?style=flat-square&logo=solid)](https://www.solidjs.com/)
[![Tailwind CSS](https://img.shields.io/badge/Style-Tailwind-38bdf8?style=flat-square&logo=tailwindcss)](https://tailwindcss.com/)

## Qué resuelve

Sevastopol es la cara visible del sistema. Toma una plataforma compleja y la convierte en una experiencia operable para personas que necesitan ejecutar tareas contables sin pelear con la arquitectura.

No intenta absorber lógica de negocio. Su trabajo es presentar, guiar, validar en superficie y delegar correctamente al backend.

## Principios del frontend

- La lógica crítica vive en el backend.
- La UI debe ser rápida incluso con dominios complejos.
- La interactividad se hidrata solo donde aporta valor real.
- La estructura visual tiene que ser mantenible, no ornamental.

## Arquitectura

El proyecto combina render del lado del servidor con islas interactivas:

- `Astro` ordena rutas, layouts y rendering base.
- `SolidJS` se usa en componentes interactivos o secciones con estado.
- La capa `api/` actúa como Backend-for-Frontend para proteger el acceso al backend real.

```text
Usuario
   -> página / isla interactiva
   -> endpoint local del frontend
   -> backend de negocio
   -> respuesta normalizada a la interfaz
```

Ese patrón permite mantener cookies, contexto y validaciones sin exponer directamente la superficie interna del backend al navegador.

Ejemplo público representativo: una persona usuaria revisa un proceso contable con validaciones, filtros y estados intermedios. La interfaz resuelve interacción y feedback, pero delega permisos, reglas y persistencia al backend a través del BFF.

## Sistema de diseño

Sevastopol sigue una jerarquía compatible con Atomic Design:

- `atoms`: piezas pequeñas y puras;
- `molecules`: combinaciones reutilizables;
- `organisms`: bloques más completos;
- `islands`: componentes que sí cargan estado e interactividad.

La separación no es estética solamente. Sirve para evitar que la UI se convierta en un contenedor caótico de lógica dispersa.

## Capas del proyecto

- sistema visual reutilizable para consistencia entre pantallas;
- islas interactivas para formularios, filtros y estados locales;
- rutas y endpoints del frontend para páginas y funciones BFF;
- layouts y composición para sostener navegación y estructura.

## Experiencia y rendimiento

Las decisiones del frontend apuntan a:

- reducir JavaScript innecesario;
- mantener tiempos de carga razonables;
- aislar la interactividad donde realmente hace falta;
- facilitar evolución visual sin romper contratos del dominio.

## Testing

El valor del frontend no está solo en verse bien. También debe sostener flujos reales:

- pruebas end-to-end para recorridos críticos;
- validación visual y funcional de componentes clave;
- control sobre regresiones en navegación, autenticación y formularios.

## Qué se publica y qué no

Esta página deja fuera:

- pantallas de clientes o datos reales;
- capturas operativas con información sensible;
- endpoints internos detallados;
- configuración privada de despliegue.

## Relación con el ecosistema

- `Orchestrator` resuelve negocio, seguridad y persistencia.
- `Nostromo` sostiene procesos de datos y automatización fuera del request-response.
- `Jean d'Arc` documenta reglas, decisiones y convenciones para desarrollo y operación.

## Estado público del proyecto

Sevastopol representa la disciplina de poner una interfaz moderna delante de un dominio serio: rápida, clara y deliberadamente separada de aquello que no le corresponde resolver.
