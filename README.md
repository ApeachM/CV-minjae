# CV — Minjae Kim

Source for <https://dev-minjae.github.io/CV-minjae/>.

## Editing

All content lives in **`_data/data.yml`**. That is the only file to edit for
content changes — nothing is hard-coded in the templates.

```
_data/data.yml          content (the single source of truth)
_layouts/resume.html    page structure
assets/css/main.scss    styles
_config.yml             site settings
```

## Local preview

```sh
docker compose up -d          # http://localhost:4000/CV-minjae/
docker compose down
```

Jekyll runs with `--watch --livereload`, so edits to `_data/data.yml` reload the
browser automatically. Changes to `_config.yml` require a `docker compose restart`.

Validate the YAML before committing — a small syntax error silently breaks the build:

```sh
python3 -c "import yaml; yaml.safe_load(open('_data/data.yml'))"
```

## PDF

Print the page from the browser (`Ctrl+P`). Print styles are in the `@media print`
block of `assets/css/main.scss`; there is no separate print page.

## Deployment

GitHub Pages builds from the `master` branch root. No CI workflow, no external
dependencies — plain Jekyll, no frameworks, no webfonts, no JavaScript.

## History

This repository began as a fork of [sharu725/online-cv](https://github.com/sharu725/online-cv)
(MIT, see `LICENSE.md`). The theme has since been fully replaced; only the
`_data/data.yml` schema still resembles the original.
