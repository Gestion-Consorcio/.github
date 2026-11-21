# Política de seguridad

## Reporte de vulnerabilidades

Si detectás una vulnerabilidad de seguridad, **no abras un issue público**. Reportala de forma privada mediante GitHub Security Advisories en el repositorio afectado o avisando directamente a las personas administradoras de la organización `Gestion-Consorcio`.

## Reglas críticas del proyecto

- Nunca subas archivos `.env`, credenciales, llaves privadas ni tokens al historial de git.
- Al procesar documentos de identidad argentinos (código PDF417), el número de trámite debe descartarse inmediatamente en memoria y jamás persistirse ni registrarse en logs.
- Validá toda entrada externa en las fronteras de confianza y respetá los límites de visibilidad entre membresías (portería, vecinos, administración y gestores).
