# Gestión Consorcio

Plataforma multi-edificio para organizar la operación diaria de un consorcio y conectar los alquileres temporales con la portería.

## Qué resuelve

- **Solicitudes y órdenes:** reclamos de vecinos con seguimiento y libro de órdenes para el encargado dentro de su horario laboral.
- **Control de acceso:** autorizaciones temporales o permanentes, padrón diario en recepción y lectura del código PDF417 del DNI argentino (descartando siempre el número de trámite).
- **Comunicación:** comunicados oficiales de la administración con confirmación de lectura.
- **Alquileres temporales:** calendario unificado por unidad, sincronización por iCal (Airbnb y Booking), pre-check-in para huéspedes y autorización automática en recepción.
- **Espacios comunes y paquetería:** agenda de turnos con lista de invitados y registro de paquetes recibidos en portería.

## Usuarios principales

| Usuario | Qué hace en la aplicación |
|---|---|
| **Vecino** (dueño o inquilino) | Reporta problemas, autoriza visitas, reserva espacios comunes, sigue paquetes y lee comunicados. |
| **Administrador** | Carga el edificio y sus unidades, gestiona reclamos, asigna órdenes o proveedores y publica comunicados. |
| **Recepción** | Consulta autorizados del día, escanea DNI, registra ingresos/egresos y recibe o entrega paquetes. |
| **Encargado** | Consulta y actualiza las órdenes de trabajo asignadas en su horario laboral. |
| **Gestor de alquileres** | Administra reservas, huéspedes y turnos de limpieza de varios departamentos, incluso si el edificio aún no usa la aplicación. |

## Repositorios y seguimiento

| Repositorio | Estado | Contenido |
|---|---|---|
| [docs](https://github.com/Gestion-Consorcio/docs) | Privado | Visión, dominio, módulos, decisiones, identidad de marca, sistema de diseño y backlog de issues |
| [frontend](https://github.com/Gestion-Consorcio/frontend) | Privado | Aplicación web (sitio público y SPA de producto) |
| [backend](https://github.com/Gestion-Consorcio/backend) | Privado | API en Go |
| [.github](https://github.com/Gestion-Consorcio/.github) | Público | Perfil de la organización y plantillas compartidas |

Seguimiento transversal de épicas y tareas: [Roadmap en GitHub Projects](https://github.com/orgs/Gestion-Consorcio/projects/1).

## Arquitectura resumida

- **Frontend:** proyecto unificado en Astro + React 19 (sitio público prerenderizado y aplicación autenticada en `/app/*`), React Aria Components, TanStack Router, TanStack Query y Paraglide JS.
- **Backend:** API independiente en Go conectada mediante contrato OpenAPI.
