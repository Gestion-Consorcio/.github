# Guía de contribución

Convenciones comunes para todos los repositorios de la organización `Gestion-Consorcio`.

## Idioma

- **Documentación, issues, interfaz de usuario, PRs y mensajes de commit:** español.
- **Código, identificadores, rutas técnicas y comentarios en el código:** inglés.

## Flujo de issues y ramas

Todo trabajo de implementación parte de un issue reclamado por quien lo ejecuta y visible en el [Roadmap](https://github.com/orgs/Gestion-Consorcio/projects/1).

### Modelo de issues en dos niveles

- **`Gestion-Consorcio/docs`:** aloja las épicas y requerimientos funcionales de producto (`#1..#66` y nuevas especificaciones).
- **`Gestion-Consorcio/frontend` y `Gestion-Consorcio/backend`:** crean issues técnicos chicos propios de cada repositorio y los enlazan como sub-issues cross-repo del requerimiento correspondiente en `docs`.

### Ciclo de trabajo

1. **Activar hooks locales (una vez por clon):**
   ```sh
   git config core.hooksPath .githooks
   ```
2. **Reclamar el issue antes de crear rama:**
   ```sh
   gh issue edit <N> --add-assignee @me
   gh issue comment <N> --body "Lo tomo."
   gh issue view <N> --json assignees --jq '.assignees[].login'
   ```
   Si hay dos personas asignadas al mismo tiempo, gana el primer comentario `"Lo tomo."` y la otra persona se quita.
3. **Crear rama vinculada al issue:**
   ```sh
   gh issue develop <N> --base main --checkout
   ```
   El hook `.githooks/pre-commit` es estricto en `frontend` y `backend` (bloquea commits en `main` y exige rama `<N>-...` con el issue asignado a tu usuario, con aviso si no hay conexión o falta `gh`) y solo advierte en `docs`.
4. **Entregar en PR chico:** un issue, un PR con `Closes #<N>` y el bloque de impacto documental completo (`impact: "updated"` o `"none"`). En `Gestion-Consorcio/docs`, el CI valida ese bloque automáticamente.
5. **Liberar si queda detenido:**
   ```sh
   gh issue edit <N> --remove-assignee @me
   gh issue comment <N> --body "Lo libero. Estado: <qué quedó hecho y qué falta>."
   ```

## Commits y Pull Requests

- Usá formato Conventional Commits: `tipo: resumen` o `tipo(alcance): resumen` (`feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`). El hook `.githooks/commit-msg` es relajado: sugiere el formato sin bloquear el commit.
- No incluyas firmas automáticas de herramientas ni `Co-Authored-By` generados por asistentes.
- Armá PRs chicos y enfocados, enlazando el issue correspondiente (`Closes #<N>`).
- No hagas `git push --force` sobre ramas compartidas ni commitees archivos de entorno o credenciales.

## Reglas centrales del dominio

1. **Permisos por membresía, nunca globales:** los roles pertenecen a la relación del usuario con un edificio o una unidad. No agregues un campo global de rol sobre el usuario.
2. **Privacidad del DNI:** al leer el código PDF417 del DNI argentino, descartá el número de trámite en memoria. Nunca se guarda en base de datos, logs ni se muestra en pantalla.
3. **Separación de flujos:** los reclamos vecinales van al administrador, nunca directo al encargado; portería no ve reclamos ni unidades sin dueño y solo accede a los datos mínimos de huéspedes.
4. **Accesibilidad:** toda vista destinada a vecinos y huéspedes prioriza tipografía amplia, contraste alto, objetivos táctiles grandes y lenguaje claro.
