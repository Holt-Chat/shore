# Shore

Shore is the web frontend for [Holt Chat](https://github.com/Holt-Chat) — a self-hostable, end-to-end encrypted chat platform. It's a static, dependency-free client (no build step) served directly by the [Keel](https://github.com/Holt-Chat/keel) backend, or by any static host pointed at a Keel instance.

## Running it

Point a Keel instance's `config.toml` at this checkout:

```toml
[frontend]
    hosted=true
    frontend_directory="../Shore"
```

Keel will then serve Shore directly — no build, bundler, or `npm install` needed. Just edit the files and reload.

## Layout

- `index.html` — HTML shell, dialogs
- `media/main.js` — UI logic: message rendering, channels/members, mentions, calls, embeds/diagrams
- `media/utility.js` — shared helpers (`sanitizeHTML`, `backendfetch`, `notice`, `affirm`, etc.)
- `media/calls.js` — WebRTC call handling
- `media/login.js` — auth/signup flow
- `media/style.css` — all styling, themed via CSS variables (`--accent`, `--bg-*`, `--text-*`, `--roundness-*`)
- `media/langs/*.json` — i18n strings
- `external/` — vendored third-party libs (markdown parser, Mermaid)

## Adding a language

Add a new file under `media/langs/` (copy `en-US.json` as a starting point) and add every key present in the other locale files — placeholders like `{}` must be preserved.

Current translations:

- en-US, es-ES, tok, uwu — Inventionpro
- fa — FrenchToblerone54
- nl-NL — MrLarso2002

## License

MIT — see [LICENSE.md](LICENSE.md).
