# Guía de contribución

Convenciones comunes para todos los repositorios de la organización `Gestion-Consorcio`.

## Idioma

- **Documentación, issues, interfaz de usuario, PRs y mensajes de commit:** español.
- **Código, identificadores, rutas técnicas y comentarios en el código:** inglés.

## Commits y Pull Requests

- Usá formato Conventional Commits: `tipo: resumen` o `tipo(alcance): resumen` (`feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`).
- No incluyas firmas automáticas de herramientas ni `Co-Authored-By` generados por asistentes.
- Armá PRs chicos y enfocados, enlazando el issue correspondiente (`Closes #<N>`).
- No hagas `git push --force` sobre ramas compartidas ni commitees archivos de entorno o credenciales.

## Reglas centrales del dominio

1. **Permisos por membresía, nunca globales:** los roles pertenecen a la relación del usuario con un edificio o una unidad. No agregues un campo global de rol sobre el usuario.
2. **Privacidad del DNI:** al leer el código PDF417 del DNI argentino, descartá el número de trámite en memoria. Nunca se guarda en base de datos, logs ni se muestra en pantalla.
3. **Separación de flujos:** los reclamos vecinales van al administrador, nunca directo al encargado; portería no ve reclamos ni unidades sin dueño y solo accede a los datos mínimos de huéspedes.
4. **Accesibilidad:** toda vista destinada a vecinos y huéspedes prioriza tipografía amplia, contraste alto, objetivos táctiles grandes y lenguaje claro.
