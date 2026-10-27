# Egyptian Arabic AI Dictionary

An Arabic, right-to-left reference for understanding AI terminology in Egyptian Arabic. The static dictionary contains **521 terms in 34 categories**, plus **37 comparisons**. Entries include English and Arabic names, definitions, practical explanations, examples, difficulty levels, and related concepts.

## Features

- Search locally in Arabic or English, including aliases; filter by category, difficulty, letter, and favorites.
- Expand cards for detailed explanations and related terms; browse comparisons, a learning path, and a quiz.
- Choose dark or light mode, adjust text size, and print the dictionary.
- Import custom entries from JSON, export custom entries as JSON, or export an HTML copy including them.
- Responsive RTL layout for desktop and mobile.

Search only uses the entries already in the browser. When no entry matches, the site explains that AI-generated explanations are currently unavailable. It does not send missing searches to an AI service.

## Run locally

From this folder run:

```sh
python -m http.server 8000
```

Open `http://localhost:8000/`. No build step, API key, or server-side application is required. The standalone `index.html` contains the interface and dictionary data.

## GitHub Pages

Put `index.html` in the publishing branch and select that branch and `/ (root)` under repository **Settings → Pages**. GitHub Pages serves the static file at the repository's Pages URL. The site does not depend on root-relative assets, so it can be served beneath a repository subpath. Changes become public after they are committed to the configured publishing source and Pages deploys them. Availability and visibility depend on the account and repository settings.

## Browser storage and custom terms

Favorites, theme, font size, and imported custom terms are stored in `localStorage` on each visitor's browser, scoped to the site's origin. They do not sync across devices or browsers and may be lost if site data is cleared. An import or favorite on one visitor's device does not change the published site for other visitors.

Open **أدوات إدارة ونشر المصطلحات** to import a JSON file, export custom terms as JSON, or export a complete HTML copy. Import accepts an array or an object with a `terms` array. Entries must pass the existing validation, including English and Arabic names, sufficiently detailed definition and explanations, and a usage context; duplicates and invalid entries are skipped. There is no manual term-entry form. Review additions before using the exported HTML as a publishing source.

## AI explanations and future integration

GitHub Pages serves static files and cannot execute the original `/api/term` backend. AI explanations are disabled because no backend or provider key is configured. A future integration needs a separately hosted server-side endpoint, server-side secret storage, input validation, abuse and rate controls, cost management, and review of generated content. Never place a provider key in this HTML, a public repository, or client-side code.

## Project files

- `index.html` — complete site and built-in dictionary data.
- `README.md` — setup, deployment, storage, and limitations.

The original supplied HTML remains in the Downloads folder; the workspace copy is the deployment candidate.
