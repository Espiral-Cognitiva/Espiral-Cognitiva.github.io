# CLAUDE.md

## Workflow de commits

Después de **cada cambio** que haga en este repo (Write/Edit/crear archivos), ejecutar automáticamente al final de la respuesta:

- `git add -A`
- `git commit -m "<mensaje conciso en imperativo>"`
- `git push origin main`

Reglas:
- Commit **directo a `main`** siempre (es la rama por defecto del repo; no hay `master`). **No** crear branches ni PRs, no sugerirlos.
- Si hay varios cambios en una misma respuesta, agruparlos en **un solo commit** al final.
- Mensaje conciso describiendo el cambio (ej: "Add note about X", "Update Y section").
- No pedir confirmación — el push es parte del flujo normal.
- Autor del commit: `git config user.email noreply@anthropic.com && git config user.name Claude` (para que GitHub lo marque como verificado).
- Al terminar de escribir o editar un post, siempre compartir el link directo en el sitio: `https://espiral-cognitiva.github.io/<año>/<mes>/<día>/<slug>.html`
