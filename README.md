# Internship Program of Web Development with HTML & CSS & JavaScript by ApexPlanet Software Pvt. Ltd.

Task 4 :-
Performance, SEO, and Accessibility optimization pass over the existing 6-page Sochit Web Studio website (Home, About, Services, Contact, Portfolio, Weather, Todo). No design, layout, color, or typography changes were made — this task is purely an under-the-hood optimization of the site built in earlier tasks.

## Pages

- `index.html` – Home
- `about.html` – About
- `services.html` – Services
- `contact.html` – Contact
- `portfolio.html` – Portfolio
- `weather.html` – Weather App
- `todo.html` – Todo List

## Folder Structure

```
Task 4/
├── index.html
├── about.html
├── services.html
├── contact.html
├── portfolio.html
├── weather.html
├── todo.html
├── README.md
├── favicon.ico
├── css/
│   ├── base.css
│   ├── navbar.css
│   ├── footer.css
│   ├── responsive.css
│   ├── home.css
│   ├── about.css
│   ├── services.css
│   ├── contact.css
│   ├── portfolio.css
│   ├── weather.css
│   └── todo.css
├── js/
│   ├── script.js
│   ├── darkmode.js
│   ├── slider.js
│   ├── storage.js
│   ├── ui.js
│   ├── validation.js
│   ├── api.js
│   ├── weather.js
│   └── todo.js
└── images/
    ├── logo.png / logo.webp
    ├── gallery1–4.jpeg / .webp
    ├── favicon-16x16.png
    ├── favicon-32x32.png
    ├── apple-touch-icon.png
    └── og-image.jpg
```

## What Changed in Task 4

### ⚡ Performance

- **WebP image conversion** — gallery and logo images now ship as `.webp` (with the original `.jpeg`/`.jpg`/`.png` kept as fallback) for smaller file sizes and faster page loads.
- **CSS deduplication & modularization** — shared rules merged out of page-specific stylesheets into common files (`base.css`, `navbar.css`, `footer.css`, `responsive.css`), removing repeated/conflicting rules across pages.
- **JavaScript DOM caching** — frequently accessed DOM elements are queried once and cached in variables instead of being re-queried on every function call, reducing redundant `document.querySelector` / `getElementById` lookups.
- **Regression fix** — a hamburger menu bug introduced while merging shared CSS was caught during testing and resolved before delivery.

### 🔍 SEO

- **Meta description length** — trimmed/rewritten on all pages to fit within the recommended ~150–160 character limit for search snippets.
- **Canonical URL formatting** — `<link rel="canonical">` tags corrected and standardized across all pages to point to the proper absolute, trailing-slash-consistent URLs.
- **Favicon rebuild** — replaced the single favicon with a full multi-resolution set (`favicon.ico`, `favicon-16x16.png`, `favicon-32x32.png`, `apple-touch-icon.png`) referenced via proper `<link rel="icon">` tags for correct rendering across browsers, tabs, and mobile home screens.
- Open Graph and Twitter Card meta tags reviewed alongside the description/canonical fixes to keep social-share previews consistent.

### ♿ Accessibility

- **Modal form (Get a Free Quote)** — identified as the primary accessibility gap; updated with proper `aria-haspopup`, `aria-controls`, and dialog-pattern attributes so screen-reader and keyboard users can open, navigate, and close it correctly.
- **ARIA roles & labels** — navigation, theme toggle, hamburger menu, and Todo filter buttons carry `aria-label`, `aria-expanded`, `aria-pressed`, and `aria-current` attributes that stay in sync with their visual state.
- **Keyboard focus management** — Back to Top and smooth-scroll anchor links move keyboard focus to the destination section/`#main-content`, not just the scroll position.
- **Semantic landmarks** — sections use `aria-labelledby` tied to their headings so the page outline is meaningful to assistive technology.

## Component Placement

| Component | Home | About | Services | Contact | Portfolio | Weather | Todo |
|---|---|---|---|---|---|---|---|
| Hamburger Menu | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Dark / Light Mode | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Back To Top Button | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Image Slider | ✅ | | | | ✅ | | |
| Modal Popup (Get a Quote) | | | ✅ | | | | |
| Form Validation | | | | ✅ | | | |
| Smooth Scrolling | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Weather App | | | | | | ✅ | |
| Todo List App | | | | | | | ✅ |

## JavaScript File Responsibilities

- `script.js` — shared page initialization (hamburger menu, nav, general setup).
- `darkmode.js` — dark/light theme toggle, persisted via `storage.js` and synced with ARIA attributes.
- `slider.js` — image slider/carousel logic for Home and Portfolio.
- `storage.js` — centralised `localStorage` helpers (`storageGet`, `storageSet`, `storageRemove`) with safe JSON parsing and a single source of truth for storage keys.
- `ui.js` — cross-page UI utilities: Back to Top button, smooth scrolling with focus management, Todo filter `aria-pressed` sync.
- `validation.js` — Contact form validation logic.
- `api.js` — `fetchWeatherData()`; wraps the OpenWeatherMap `fetch()` call with error handling.
- `weather.js` — Weather page controller: renders results, loading state, and last-searched-city persistence.
- `todo.js` — Todo List app: add/edit/delete/toggle tasks, filters, clear completed, task counter, persistence.
