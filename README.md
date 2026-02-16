# Secrets — a Slug web app (teaching example)

This repository is a small, intentionally simple **teaching project** that demonstrates how to build a web application
using **Slug**. It uses:

- a small server configured via `slug.toml`
- **Mustache** templates for HTML rendering
- a `static/` directory for assets (CSS, images, etc.)

The app is named **“secrets”** and is structured to be easy to read, modify, and extend during a lesson.

---

## Project layout

High-level structure:

- `secrets.slug` — the Slug application entry point / main app definition
- `slug.toml` — configuration (host/port, app settings)
- `views/` — Mustache templates
    - `layouts/` — shared page layouts (e.g., the main layout wrapper)
    - `pages/` — full pages (organized by page/route)
    - `partials/` — reusable fragments (footer, headers, etc.)
- `static/` — static files served directly (CSS, images, client-side JS)

---

## Configuration

The app is configured in `slug.toml`. By default, it binds to localhost on port 8080:

- address: `127.0.0.1`
- port: `8080`

If you need to run multiple copies at once, change the port.

---

## Running the app

To run the app locally,

```bash
slug secrets.slug
```

then open:

- http://127.0.0.1:8080

---

## Templates (Mustache)

This project uses Mustache templates under `views/`.

Typical pattern:

- a **layout** provides the shared HTML skeleton (head, nav, footer)
- each **page** provides the content for a specific route/view
- **partials** keep shared snippets DRY (e.g., footer)

If you’re new to Mustache, the main idea is:

- templates are mostly HTML
- variables are inserted with `{{name}}`
- sections/loops are handled with `{{#items}} ... {{/items}}`

---

## Static assets

Put files like CSS and images under `static/`. These are served directly (no templating), which makes them ideal for:

- stylesheets
- images
- client-side scripts

---

## Learning goals (what to explore)

Suggested “try this next” exercises:

1. **Change the home page content** in the relevant `views/pages/...` templates.
2. Add a new **partial** and include it from multiple pages.
3. Add a stylesheet under `static/` and wire it into the main layout.
4. Change the port in `slug.toml` and confirm it binds correctly.
5. Add a new page/template and connect it to a new route (as taught in your Slug lessons).

---

## Troubleshooting

- **Port already in use**: change `port` in `slug.toml` to another value (e.g., 8081).
- **Can’t connect in browser**: confirm you’re visiting `http://127.0.0.1:8080` (and that the app is running).
- **Templates not updating**: restart the app if your setup doesn’t support hot reload.

---

## License / usage

This is a teaching example. Use it freely for learning and experimentation.
