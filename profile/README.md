# Biblioteca: Sistema de Préstamos y Multas

[![Estado](https://img.shields.io/badge/Estado-MVP%20funcional-2563eb?style=flat-square)](https://github.com/orgs/TallerS7-Expectativa-vs-Realidad/projects/2/views/1)
[![Backend](https://img.shields.io/badge/Backend-Node.js%20%2B%20Express-3c873a?style=flat-square)](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Backend-Sis-Prestamos-y-Multas/tree/develop)
[![Frontend](https://img.shields.io/badge/Frontend-React%20%2B%20Vite-0f766e?style=flat-square)](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Frontend-Sis-Prestamos-y-Multas)
[![Base de datos](https://img.shields.io/badge/DB-PostgreSQL-336791?style=flat-square)](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/tree/develop)
[![QA](https://img.shields.io/badge/QA-K6%20%7C%20Karate-7c3aed?style=flat-square)](https://github.com/orgs/TallerS7-Expectativa-vs-Realidad/repositories)

Espacio principal del taller para el proyecto Biblioteca, enfocado en construir un MVP funcional para la gestión de préstamos, devoluciones tardías y multas de lectores.

El trabajo del equipo se distribuye entre documentación funcional, implementación técnica, interfaz web y automatización de pruebas, manteniendo trazabilidad entre historias, subtareas y evidencia QA.

**Accesos rápidos:** [Repositorios del proyecto](#repositorios-del-proyecto) · [Documentación clave](#documentación-clave) · [Cómo levantar el proyecto con Docker](#cómo-levantar-el-proyecto-con-docker) · [Historias principales del MVP](#historias-principales-del-mvp)

---

## Repositorios del proyecto

| Recurso | Descripción | Acceso |
| --- | --- | --- |
| Arquitectura y documentación | PRD, historias de usuario, subtareas, plan de pruebas, casos de prueba y guías del taller | [S7-Arquitectura](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/tree/develop) |
| Backend | API REST para préstamos, devoluciones, préstamos vencidos y pago de multas | [S7-Backend-Sis-Prestamos-y-Multas](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Backend-Sis-Prestamos-y-Multas/tree/develop) |
| Frontend | Aplicación React para operar el flujo del sistema desde interfaz web | [S7-Frontend-Sis-Prestamos-y-Multas](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Frontend-Sis-Prestamos-y-Multas) |
| Pruebas K6 | Suite de pruebas de carga y rendimiento para los endpoints del sistema | [S7-K6-Sis-Prestamos-y-Multas](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-K6-Sis-Prestamos-y-Multas) |
| Pruebas Karate | Automatización de pruebas API para escenarios funcionales del MVP | [S7-Karate-Sis-Prestamos-y-Multas](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Karate-Sis-Prestamos-y-Multas) |
| GitHub Project | Tablero de seguimiento del taller y organización del backlog | [Project Biblioteca](https://github.com/orgs/TallerS7-Expectativa-vs-Realidad/projects/2/views/1) |

---

## Qué resuelve este sistema

El MVP del taller cubre el flujo principal de una biblioteca académica:

- consultar si un libro está disponible o prestado;
- registrar préstamos con plazos válidos;
- detectar devoluciones fuera de tiempo;
- calcular multas por mora;
- bloquear nuevos préstamos cuando el lector tiene deuda pendiente;
- rehabilitar al lector una vez paga la multa completa.

---

## Documentación clave

La base funcional y técnica del proyecto vive en el repositorio de arquitectura:

| Documento | Propósito | Enlace |
| --- | --- | --- |
| PRD | Visión del producto, alcance, reglas de negocio y riesgos | [PRD.md](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/blob/develop/PRD.md) |
| USER_STORIES | Historias del MVP con criterios de aceptación y escenarios | [USER_STORIES.md](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/blob/develop/USER_STORIES.md) |
| SUBTASKS | Desglose operativo para trabajo DEV y QA | [SUBTASKS.md](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/blob/develop/SUBTASKS.md) |
| TEST_PLAN | Estrategia general de validación del sistema | [TEST_PLAN.md](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/blob/develop/TEST_PLAN.md) |
| TEST_CASES | Casos de prueba detallados para el MVP | [TEST_CASES.md](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/blob/develop/TEST_CASES.md) |
| REALITY_CHECK | Resumen del trabajo iterativo y reflexión del sprint | [REALITY_CHECK.md](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/blob/develop/REALITY_CHECK.md) |
| CONTRIBUTING | Reglas de colaboración y organización del trabajo | [CONTRIBUTING.md](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura/blob/develop/CONTRIBUTING.md) |

---

## Cómo levantar el proyecto con Docker

El punto de entrada para ejecutar el sistema en local es el repositorio de arquitectura, porque centraliza la orquestación del entorno.

### 1. Clonar el repositorio de arquitectura

```bash
git clone https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Arquitectura.git
cd S7-Arquitectura
git checkout develop
```

### 2. Levantar el entorno completo

```bash
docker compose up -d
```

### 3. Levantar el entorno de desarrollo

```bash
docker compose -f docker-compose.dev.yml up
```

### 4. Verificar servicios disponibles

| Servicio | URL | Uso |
| --- | --- | --- |
| Frontend | http://localhost:8080 | Interfaz web del sistema |
| Backend | http://localhost:3000/health | Health check de la API |
| PostgreSQL | localhost:5432 | Base de datos del entorno local |

### 5. Detener el entorno

```bash
docker compose down
```

---

## Historias principales del MVP

- HU-01: Consultar estado y disponibilidad de un libro.
- HU-02: Registrar préstamo de un libro disponible a un lector habilitado.
- HU-03: Registrar devolución de un libro dentro del plazo.
- HU-04: Registrar devolución tardía y generar multa.
- HU-05: Consultar libros fuera de plazo y lector responsable.
- HU-06: Registrar el pago total de una multa y rehabilitar al lector.

---

## Organización del trabajo

- Organización GitHub: [TallerS7-Expectativa-vs-Realidad](https://github.com/orgs/TallerS7-Expectativa-vs-Realidad/repositories)
- Tablero del proyecto: [Project Biblioteca](https://github.com/orgs/TallerS7-Expectativa-vs-Realidad/projects/2/views/1)
- Repositorio de automatización Karate: [README Karate](https://github.com/TallerS7-Expectativa-vs-Realidad/S7-Karate-Sis-Prestamos-y-Multas/blob/main/README.md)

---

## Equipo

### Desarrollo

- [Gabriel Perero](https://github.com/GabrielGNP)

### Quality Assurance

- [Alexander Molina](https://github.com/AlexRieger47)
