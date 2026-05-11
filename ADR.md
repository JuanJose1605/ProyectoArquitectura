# ADR-001 — Implementación de Arquitectura Cliente-Servidor

## Estado del ADR
### Implementado

---

## Contexto

### Objetivo del ADR
Definir una arquitectura que permita separar la interfaz de usuario, la lógica de negocio y la persistencia de datos para mejorar la escalabilidad, mantenibilidad y organización del sistema SIWVENTAS.

### Diagnóstico del sistema
El proyecto requiere:
- Acceso desde dispositivos móviles.
- Gestión centralizada de productos y pedidos.
- Escalabilidad para futuras funcionalidades.
- Separación clara entre frontend y backend.

### Stack tecnológico actual
- Frontend: Ionic + React
- Backend: NestJS
- Base de datos: PostgreSQL
- ORM: Prisma
- Infraestructura: Docker + AWS

---

## Decisión

### A) Patrón/SOLID
Arquitectura Cliente-Servidor + Separación de Responsabilidades

### B) Dónde
Estructura general del sistema SIWVENTAS.

### C) Problema actual
Una arquitectura monolítica dificulta la escalabilidad, mantenimiento y reutilización de componentes.

### D) Decisión
Implementar una arquitectura cliente-servidor separando:
- Frontend móvil/web
- Backend API REST
- Base de datos PostgreSQL

### E) Beneficio
- Mayor escalabilidad.
- Mejor mantenibilidad.
- Separación clara de responsabilidades.
- Posibilidad de desplegar servicios independientemente.

---

# ADR-002 — Uso de Ionic + React para Frontend

## Estado del ADR
### Implementado

---

## Contexto

### Objetivo del ADR
Seleccionar una tecnología frontend moderna, reutilizable y compatible con dispositivos móviles.

### Diagnóstico
El sistema requiere:
- Interfaz intuitiva.
- Compatibilidad móvil.
- Componentes reutilizables.
- Navegación fluida.

---

## Decisión

### A) Patrón/SOLID
Arquitectura basada en componentes reutilizables.

### B) Dónde
Frontend del sistema SIWVENTAS.

### C) Problema actual
Desarrollar aplicaciones móviles nativas incrementa tiempo y costos de desarrollo.

### D) Decisión
Utilizar Ionic + React para construir una aplicación híbrida multiplataforma.

### E) Beneficio
- Desarrollo rápido.
- Reutilización de componentes.
- Compatibilidad Android/Web.
- Mejor experiencia de usuario.

---

# ADR-003 — Uso de NestJS para Backend

## Estado del ADR
### Implementado

---

## Contexto

### Objetivo del ADR
Implementar un backend modular y escalable para la gestión de usuarios, productos y pedidos.

### Diagnóstico
El sistema necesita:
- Organización modular.
- APIs REST seguras.
- Escalabilidad futura.

---

## Decisión

### A) Patrón/SOLID
Arquitectura Modular + SRP.

### B) Dónde
Backend de SIWVENTAS.

### C) Problema actual
Backends no estructurados generan código difícil de mantener.

### D) Decisión
Utilizar NestJS organizado por módulos:
- AuthModule
- ProductsModule
- OrdersModule
- UsersModule

### E) Beneficio
- Código mantenible.
- Separación de responsabilidades.
- Escalabilidad.
- Integración sencilla con JWT y Prisma.

---

# ADR-004 — Uso de PostgreSQL como Base de Datos

## Estado del ADR
### Implementado

---

## Contexto

### Objetivo del ADR
Garantizar persistencia segura y eficiente de la información del sistema.

### Diagnóstico
El proyecto maneja:
- Relaciones entre entidades.
- Pedidos.
- Inventario.
- Usuarios y autenticación.

---

## Decisión

### A) Patrón/SOLID
Persistencia relacional.

### B) Dónde
Capa de datos del sistema.

### C) Problema actual
Bases de datos no relacionales complican consultas relacionales complejas.

### D) Decisión
Utilizar PostgreSQL como motor principal de base de datos.

### E) Beneficio
- Integridad de datos.
- Alto rendimiento.
- Soporte para relaciones complejas.
- Seguridad y estabilidad.

---

# ADR-005 — Implementación de Prisma ORM

## Estado del ADR
### Implementado

---

## Contexto

### Objetivo del ADR
Simplificar la interacción entre el backend y PostgreSQL.

### Diagnóstico
Las consultas SQL manuales aumentan errores y complejidad.

---

## Decisión

### A) Patrón/SOLID
ORM + Abstracción de persistencia.

### B) Dónde
Backend NestJS.

### C) Problema actual
Consultas repetitivas y difíciles de mantener.

### D) Decisión
Utilizar Prisma ORM para manejar entidades y consultas.

### E) Beneficio
- Menos errores SQL.
- Tipado seguro.
- Mayor productividad.
- Código más limpio.

---

# ADR-006 — Uso de JWT para Autenticación

## Estado del ADR
### Implementado

---

## Contexto

### Objetivo del ADR
Garantizar autenticación segura entre cliente y servidor.

### Diagnóstico
El sistema necesita:
- Login seguro.
- Protección de rutas administrativas.
- Manejo de sesiones modernas.

---

## Decisión

### A) Patrón/SOLID
Autenticación Stateless + SRP.

### B) Dónde
Módulo de autenticación.

### C) Problema actual
Las sesiones tradicionales dificultan escalabilidad.

### D) Decisión
Implementar autenticación mediante JWT.

### E) Beneficio
- Seguridad.
- Escalabilidad.
- Compatibilidad con APIs REST.
- Protección de endpoints.

---

# ADR-007 — Uso de Docker para Contenedorización

## Estado del ADR
### Propuesto

---

## Contexto

### Objetivo del ADR
Facilitar despliegue y portabilidad del sistema.

### Diagnóstico
Configurar entornos manualmente genera inconsistencias.

---

## Decisión

### A) Patrón/SOLID
Contenedorización.

### B) Dónde
Infraestructura del sistema.

### C) Problema actual
Diferencias entre entornos de desarrollo y producción.

### D) Decisión
Utilizar Docker y Docker Compose para ejecutar:
- Frontend
- Backend
- PostgreSQL

### E) Beneficio
- Despliegue rápido.
- Entornos consistentes.
- Escalabilidad.
- Facilidad de mantenimiento.

---

# ADR-008 — Implementación de Infraestructura en AWS

## Estado del ADR
### Propuesto

---

## Contexto

### Objetivo del ADR
Desplegar SIWVENTAS en una infraestructura cloud segura y escalable.

### Diagnóstico
El sistema requiere:
- Alta disponibilidad.
- Escalabilidad.
- Seguridad.
- Monitoreo.

---

## Decisión

### A) Patrón/SOLID
Arquitectura Cloud.

### B) Dónde
Infraestructura general del sistema.

### C) Problema actual
Infraestructura local limita disponibilidad y crecimiento.

### E) Beneficio
- Escalabilidad.
- Alta disponibilidad.
- Seguridad.
- Monitoreo empresarial.
- Mejor rendimiento.