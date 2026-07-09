<div align="center">
  <img src="https://raw.githubusercontent.com/Holt-Chat/shore/main/media/holt.png" width="96" alt="Holt Chat logo">

  # Shore

  **The web frontend for [Holt Chat](https://github.com/Holt-Chat)**, a self-hostable, end-to-end encrypted chat platform.

  [![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE.md)
  [![No build step](https://img.shields.io/badge/build-none-009688?style=flat-square)](#running-it)
  [![E2EE](https://img.shields.io/badge/encryption-E2EE-6f42c1?style=flat-square)](#)
</div>

---

Shore is a static, dependency-free client. No bundler, no build step, no `npm install`. It's served directly by the [Keel](https://github.com/Holt-Chat/keel) backend, or by any static host pointed at a Keel instance.

## Running it

Point a Keel instance's `config.toml` at this checkout:

```toml
[frontend]
    hosted=true
    frontend_directory="../Shore"
```

Keel will then serve Shore directly. Just edit the files and reload.

## Layout

| Path | Purpose |
|---|---|
| `index.html` | HTML shell, dialogs |
| `media/main.js` | UI logic: message rendering, channels/members, mentions, calls, embeds/diagrams |
| `media/utility.js` | Shared helpers (`sanitizeHTML`, `backendfetch`, `notice`, `affirm`, etc.) |
| `media/calls.js` | WebRTC call handling |
| `media/login.js` | Auth/signup flow |
| `media/style.css` | All styling, themed via CSS variables (`--accent`, `--bg-*`, `--text-*`, `--roundness-*`) |
| `media/langs/*.json` | i18n strings |
| `external/` | Vendored third-party libs (markdown parser, Mermaid) |

## Adding a language

Add a new file under `media/langs/` (copy `en-US.json` as a starting point) and add every key present in the other locale files. Placeholders like `{}` must be preserved.

Current translations:

| Locale | Contributor |
|---|---|
| en-US, es-ES, tok, uwu | Inventionpro |
| fa | FrenchToblerone54 |
| nl-NL | MrLarso2002 |

## License

MIT, see [LICENSE.md](LICENSE.md).
