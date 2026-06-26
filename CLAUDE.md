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
- Al terminar de escribir o editar un post, siempre compartir el link directo en el sitio: `https://espiral-cognitiva.github.io/<año>/<mes>/<día>/<slug>/`
- El sitio siempre debe tener `jekyll-sitemap` en `Gemfile` (grupo `:jekyll_plugins`) y en `plugins:` de `_config.yml`. Si alguno falta, agregarlo en el mismo commit.

## Autoría y contenido

Todo post debe estar inspirado en una interacción real con el usuario (conversación, reflexión compartida, pregunta concreta). Reglas:
- **Nunca inventar contenido desde cero.** Sin conversación real de respaldo, no hay post.
- Claude puede elaborar, estructurar y desarrollar — pero máximo ~30% del contenido puede ser aporte propio. El 70%+ debe provenir de ideas, frases o preguntas reales del usuario.
- Si el usuario pasa un hilo o conversación, usarlo como fuente primaria. Citar o parafrasear ideas del hilo, no reemplazarlas con versiones genéricas.
- Si no hay conversación real para un tema, decirlo y pedirla antes de escribir.

## Guía de escritura

La guía completa de estilo, tono y estructura está en `_includes/como-escribir.md`. Leerla antes de escribir cualquier post. La persona/voz del blog está en `_includes/gpt.md`.

Reglas operativas clave (resumen):

**Títulos:** formato de dos partes `"Concepto: Provocación"` — ej: "Ley de Murphy Inversa: Forjando la Realidad". El separador es siempre `:`. Series usan prefijo consistente ("Diálogo con X:", "Manifiesto X:").

**Frontmatter obligatorio:**
```yaml
layout: post
title: "Título: Subtítulo provocador"
date: YYYY-MM-DD 10:00:00 +0200
categories: categoria1 categoria2 mente-abierta  # o apto-para-todos
```
- Sin campo `author` (blog pseudónimo).
- Categorías en minúsculas con guiones, separadas por espacios (no arrays).
- Última categoría indica la colección: `mente-abierta` (contenido complejo) o `apto-para-todos` (accesible).

**Estructura del post:**
- Apertura con gancho: pregunta, escenario o afirmación provocadora.
- Secciones con `##` — sin repetir el título del frontmatter.
- Cierre obligatorio: pregunta provocadora al lector, llamado a la acción, o frase corta de "golpe seco".

**Tono:** provocador, riguroso, visual, confrontacional pero no condescendiente. Sin misticismo barato, sin autoayuda vacía, sin clichés.

**Lenguaje fuerte sin vulgaridad:** se busca intensidad, no groserías. Antes de **cada commit** que toque un post, revisar groserías contra la tabla de equivalencias de `_includes/como-escribir.md` (sección "Lenguaje fuerte sin vulgaridad") y reemplazarlas (`mierda`→`porquería`/`demonios`, `jodido`→`increíble`/`brutal`, etc.). Aplica incluso a frases citadas del usuario: preservar la fuerza, no la grosería.

**Español neutro:** preferir español neutro y entendible en cualquier país hispanohablante; evitar regionalismos y jerga local (ej. "jalón de chuleta", "cachete", "achorado") salvo que el término sea muy importante para el sentido — en ese caso, pedir confirmación al usuario antes de usarlo. Aunque el usuario escriba en jerga peruana/arequipeña, traducir a términos neutros en el post.

**"Carnecita":** preferir borrador denso y rico sobre concisión superficial. El usuario edita después; Claude no auto-censura por extensión.

## Pseudonimato

El blog es pseudónimo. Reglas para preservarlo:
- Nunca mencionar nombre real, apellido, email personal ni empresa (Apurata) en ningún archivo del repo (posts, about, config, comentarios de código, etc.).
- El autor público es siempre **"Espiral Cognitiva"** con email `espiralcognitiva@gmail.com`.
- Mis commits usan `noreply@anthropic.com / Claude` — nunca datos del usuario real.
- Si al revisar un archivo se detecta PII (nombre, empresa, email personal), eliminarlo antes de commitear.
