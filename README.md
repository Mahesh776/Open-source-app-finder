# Open Source Universe

> **Discover. Understand. Compare. Build. Learn. Contribute.**

A continuously growing, structured index of the open source ecosystem. Search, compare, and explore open source software — from AI models and developer tools to games, self-hosted services, and creative software.

![Open Source Universe](https://img.shields.io/badge/status-Phase%201-7c5cff) ![Static site](https://img.shields.io/badge/deploy-GitHub%20Pages-22d3ee) ![No tracking](https://img.shields.io/badge/privacy-no%20tracking-3ddc97)

---

## Features (Phase 1)

- **Premium homepage** with hero search, categories, trending, hidden gems, and curated collections.
- **Universal search** with natural-language hints (category, platform, license), fuzzy-ish matching, and debounced input.
- **Advanced filters** for category, platform, language, license, status, and sort order. Shareable search URLs.
- **Project detail pages** with Overview, Project DNA, Project X-Ray, alternatives, related projects, and collections.
- **Compare** up to 4 projects side-by-side with factual, structured fields — no arbitrary "winner".
- **Favorites, collections, and recent** stored locally in the browser. No account required.
- **Command palette** (`Ctrl/Cmd + K`) for fast navigation.
- **Dark / light / system themes** with persistence.
- **Responsive design** tuned for mobile, tablet, laptop, and desktop.
- **Accessibility**: semantic HTML, keyboard navigation, focus states, ARIA, skip link, reduced motion support.
- **Performance**: no frameworks, vanilla JS, debounced search, lazy-friendly markup, small footprint.
- **GitHub Pages ready**: hash-based routing with `404.html` SPA fallback.
- **PWA-ready**: `manifest.json` included.

## Live demo

Deploy to GitHub Pages:

1. Push this repository to GitHub.
2. In repository settings, enable **Pages** → deploy from branch `main` (root).
3. Visit `https://<user>.github.io/<repo>/`.

## Folder structure

```
.
├── index.html            # App shell
├── 404.html              # SPA fallback for GitHub Pages
├── manifest.json         # PWA manifest
├── README.md
├── css/
│   └── styles.css        # Design system + components
├── js/
│   ├── data.js           # Projects, categories, collections
│   ├── search.js         # Client-side search engine
│   └── app.js            # Router, views, theme, favorites, compare
└── assets/
    └── icons/            # (reserved for future icons)
```

## Data model

Each project in `js/data.js` follows this schema:

```json
{
  "id": "ollama",
  "name": "Ollama",
  "slug": "ollama",
  "description": "…",
  "category": "ai",
  "subcategories": ["local-ai", "inference"],
  "tags": ["llm", "local", "inference", "api"],
  "platforms": ["Linux", "macOS", "Windows"],
  "license": "MIT",
  "languages": ["Go"],
  "technologies": ["Go", "C++"],
  "repository": "https://github.com/ollama/ollama",
  "officialWebsite": "https://ollama.com",
  "documentation": "…",
  "status": "active",
  "metrics": { "source": "github", "host": "github" },
  "lastUpdated": "2026-09",
  "dataSources": ["github"]
}
```

Metrics such as stars/forks are intentionally **not** fabricated. A future pipeline will populate them from public APIs.

## Development

```bash
# Any static server works. Examples:
python3 -m http.server 8000
npx serve .
```

Then open `http://localhost:8000`.

## URLs

- `#/` — Home
- `#/search?q=…` — Search with optional filters (`category`, `platform`, `language`, `license`, `status`, `sort`)
- `#/categories` — All categories
- `#/category/:id` — Category listing
- `#/project/:slug` — Project detail
- `#/compare` — Compare selected projects
- `#/favorites` — Saved projects
- `#/collections` — All collections
- `#/collection/:id` — Collection detail
- `#/trending`, `#/gems`, `#/recent`, `#/ai`, `#/games`, `#/selfhosted`, `#/dev`
- `#/devices` — Device profile (future-ready)
- `#/about` — About

## Roadmap

- **Phase 2** — Advanced filters UI polish, SEO meta per project, performance profiling.
- **Phase 3** — Automated metadata pipeline (GitHub/GitLab/Codeberg), validation, duplicate detection, GitHub Actions.
- **Phase 4** — AI-assisted discovery, recommendations, knowledge graph visualization, stack builder.
- **Phase 5** — Community submissions, accounts, collection sync, maintainer verification, watchlists.
- **Phase 6** — Public API, full PWA offline caching, browser extension, mobile app.

## Contributing

Contributions are welcome. Please:

- Keep project metadata factual. Do not invent stars, downloads, or compatibility.
- Validate URLs and licenses before adding a project.
- Respect API terms of external sources.
- Open an issue before large architectural changes.

## License

The code in this repository is released under the MIT License. Project metadata references third-party open source projects under their respective licenses.