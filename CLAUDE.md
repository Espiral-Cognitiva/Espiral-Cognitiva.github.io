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
- El sitio siempre debe tener `jekyll-sitemap` en `Gemfile` (grupo `:jekyll_plugins`) y en `plugins:` de `_config.yml`. Si alguno falta, agregarlo en el mismo commit.

## Autoría y contenido

Todo post debe estar inspirado en una interacción real con el usuario (conversación, reflexión compartida, pregunta concreta). Reglas:
- **Nunca inventar contenido desde cero.** Sin conversación real de respaldo, no hay post.
- Claude puede elaborar, estructurar y desarrollar — pero máximo ~30% del contenido puede ser aporte propio. El 70%+ debe provenir de ideas, frases o preguntas reales del usuario.
- Si el usuario pasa un hilo o conversación, usarlo como fuente primaria. Citar o parafrasear ideas del hilo, no reemplazarlas con versiones genéricas.
- Si no hay conversación real para un tema, decirlo y pedirla antes de escribir.

## Pseudonimato

El blog es pseudónimo. Reglas para preservarlo:
- Nunca mencionar nombre real, apellido, email personal ni empresa (Apurata) en ningún archivo del repo (posts, about, config, comentarios de código, etc.).
- El autor público es siempre **"Espiral Cognitiva"** con email `espiralcognitiva@gmail.com`.
- Mis commits usan `noreply@anthropic.com / Claude` — nunca datos del usuario real.
- Si al revisar un archivo se detecta PII (nombre, empresa, email personal), eliminarlo antes de commitear.
