# Ntarstudio Official Site — NT-Studio

**English** | [简体中文](README.md)

The official brand homepage of Ntarstudio (星玖工作室), which also serves as the unified entry point to three in-house projects. The site is a single-page static application: it depends on no front-end framework, has no build pipeline and no back-end service, and renders all of its content locally in the browser.

| Item | Content |
| --- | --- |
| Full project name | Ntarstudio Official Site |
| Project code | NT-Studio |
| Live URL | https://www.ntars.cn/ |
| Source repository | https://github.com/ntars/NT-Studio |
| Site form | Single-page static site (SPA-lite) · installable PWA |
| Page footprint | 1 HTML file · 1 main stylesheet · 6 page scripts · 1 Service Worker |
| License of first-party code | MIT |
| License of derived portions | Apache License 2.0 |
| ICP filing number | 蜀ICP备2026027050号 |
| Copyright | Copyright (c) 2024–2026 Ntarstudio |

---

## 1. Project Description

### 1.1 Positioning

This project is Ntarstudio's brand frontage and project distribution entry point, and it addresses three concerns:

1. **Brand recognition**: establish the correspondence among the three name forms—Ntarstudio (星玖工作室), Ntarstudio and Ntars—on the first screen;
2. **Project navigation**: direct visitors to the official addresses of the three operating projects and state each project's launch status truthfully;
3. **Information accuracy**: nothing offline or not yet launched appears in the page or in its metadata, so no dead links are produced and no misleading information is created.

The site uses no CMS and integrates no comments, analytics, advertising or any third-party script (except Typed.js, see Chapter 4). All copy and links are maintained directly in `index.html`, and changes take effect immediately.

### 1.2 Scope Boundaries

**This project is responsible for**: brand presentation, project navigation, aggregation of contact information, PWA installability, and structured descriptions for search engines.

**This project is not responsible for**:

- hosting any concrete functionality of the sub-projects, each of which has its own domain, its own repository and its own license;
- collecting user data: there is no account system, no form submission and no cookie writing;
- providing a content management back end; page updates are made through Git commits.

### 1.3 The Operating Projects

| Project | Positioning | Form | Status | Official address | Code license |
| --- | --- | --- | --- | --- | --- |
| **Xael (玄玖灵犀, NT-Xhex)** | Tool for compiling, textually collating and digitally computing traditional Chinese shushu literature | WeChat Mini Program (primary) · browser PWA · uni-app multi-platform · AI / CLI invocation | Product live (v4.3.0), official site in preparation | [github.com/ntars/Xael](https://github.com/ntars/Xael) (switches to the official site once `x.ntars.cn` goes live) | AGPL-3.0 |
| **Ondra (元鸣)** | Desktop AI anthropomorphic companion (personality, memory, emotion, voice and appearance; stack includes the NT-Dpet distribution and the NT-Sine local model) | Electron desktop · local deployment (Apple Silicon / MLX) | Official site live (`ai.ntars.cn`), software unreleased | [ai.ntars.cn](https://ai.ntars.cn/) | AGPL-3.0-or-later / AGPL-3.0 |

The status labels of both projects follow the same principle: **distinguish "site status" from "product status"**.

- Xael (NT-Xhex): the product itself (v4.3.0, `version.json` as the single version source of truth) is live on its platforms; its official site `x.ntars.cn` had no DNS A record as of 2026-10-27 and does not resolve publicly, so the card carries no site link and the status is stated as "product live, official site in preparation"; the card will switch to the site address once it goes live.
- Ondra: the official site `ai.ntars.cn` (the NT-Sine site) resolves and is deployed and reachable, and the card says "official site live"; the desktop software itself (NT-Dpet, currently 0.3.0 S0) is unreleased and has no installable artifact, stated separately from the site status so that visitors do not mistake the existence of a site for a usable product.

### 1.4 Discontinued Projects

The following projects are no longer operating and their domains no longer resolve; they have been removed from the page body and from all metadata. They are recorded here to explain the difference between historical information and the current position:

| Former project | Former domain | Current status | Handling |
| --- | --- | --- | --- |
| NT-Know (玄玖知识库) | `k.ntars.cn` | Offline, no DNS A record | Card, meta, keywords, JSON-LD all removed |
| NT-List (玄玖测试库) | `q.ntars.cn` | Offline, no DNS A record | Card, meta, keywords, JSON-LD all removed |

If these names appear on other pages, in search-engine snapshots or in older screenshots, that information is outdated; this page and the three official project addresses are authoritative.

---

## 2. Site Structure

### 2.1 Page Composition

From top to bottom the page consists of five blocks, all static, with no routing:

| Block | Content | Interaction |
| --- | --- | --- |
| Greeting | "Hi, I'm Ntars" / "Hi, We're Ntarstudio" plus looping typewriter copy | Clicking the name switches between personal and studio mode; double-clicking "A Ntarstudio Production" switches the theme |
| Divider | A horizontal dashed line that visually separates the brand area from the project area | None |
| Projects | The heading "A Ntarstudio Production" plus three project cards | The hover glow follows the pointer; clicking opens a new window |
| Contact us | A fixed text entry point in the top-right corner plus a modal dialog | Opens on click/Enter; closes via the overlay, the close button or `Esc` |
| Footer | ICP filing number plus copyright line | The filing number links to the MIIT filing system |

Overlays: a full-screen `canvas` firework particle layer, fixed-position bottom decorations (glow, rising stars, earth circle) and a background dot matrix.

### 2.2 Directory Structure

```
NT-Studio/
├── index.html                            # Page structure, metadata, inline logic (theme init, device detection, modal, PWA registration)
├── manifest.json                         # PWA manifest: name, icons, launch mode, theme color
├── sw.js                                 # Service Worker: precache, cache-first, background update, stale-cache cleanup
├── README.md                             # This document
├── LICENSE                               # Full MIT license text (first-party code)
├── LICENSE-Apache-2.0.txt                # Full Apache-2.0 license text (portions derived from asorn/asorn-open)
├── NOTICE                                # Copyright and third-party component notices (legal document)
├── 开源方案扫描.md                        # Open-source component survey across the three projects (adopt now / evaluate / unavailable)
├── baidu_verify_codeva-C4tp7NQbk5.html   # Baidu Search Resource Platform site verification file
├── tencent-cloud-config.yml              # Supplementary config for Tencent Cloud COS deployment (not used by this project)
└── assets/
    ├── css/
    │   ├── base.css                      # The only stylesheet loaded by the page
    │   ├── base.scss                     # Legacy stylesheet source from the base period, not referenced
    │   └── base.min.css                  # Legacy minified artifact, not referenced
    ├── js/
    │   ├── security.js                   # Security: blocks selection, copying, context menu and shortcuts; tamper monitoring
    │   ├── app.min.js                    # Card glow: writes pointer coordinates into CSS variables
    │   ├── anime.js                      # anime.js v2.0.2 (third-party, MIT)
    │   ├── firework.js                   # Firework particles: triggered by click/touch
    │   ├── trail.js                      # Pointer trail: pointer movement spawns gradient particles
    │   └── bg.js                         # Background particles: floating nodes and links, repelled by the pointer
    └── img/
        ├── icon.svg                      # Primary icon (SVG, preferred favicon)
        ├── favicon-color.svg             # Color site icon
        ├── apple-touch-icon.png          # iOS home-screen icon 180×180
        ├── icon-192.png                  # PWA icon 192×192
        └── icon-512.png                  # PWA icon 512×512
```

On `base.scss` and `base.min.css`: both derive from the asorn/asorn-open base period and are out of sync with the current styles (`base.scss` still contains modules such as about and blog that this site does not use). They take no part in any build and are referenced by no page; they are kept because files carrying traces of an upstream source should not be deleted at will. Once there is no need to trace them, they can be removed together in a separate commit.

### 2.3 Build and Run

This project has no build step, no package-manager dependencies and no compiled artifacts. `index.html` is the final artifact and can be served directly by a static server. Style changes are made by editing `assets/css/base.css` directly.

---

## 3. Features and Implementation Details

### 3.1 Theme System

**Resolution order** (executed synchronously by an inline script inside `<head>`, before the stylesheet loads):

1. Read `window.matchMedia('(prefers-color-scheme: dark)')`. If the media query is usable (`media !== 'not all'`), take the system preference;
2. If it is not usable, fall back to local time: 6:00–18:00 is light, all other hours are dark;
3. Write the result into `<html data-theme>` and also set `color-scheme`, so that form controls and scrollbars follow the theme.

**First-frame flash prevention**: the script first adds a `theme-lock` class to `<html>`, and the stylesheet suppresses transitions while that class is present; after the theme is written, the class is removed on two consecutive `requestAnimationFrame` frames. The purpose is to avoid the white flash caused by the browser painting the first frame in the default color and then switching instantly.

**Manual toggle**: double-clicking the "A Ntarstudio Production" heading flips `data-theme` and updates `<meta name="theme-color">` in step, so that the address-bar color matches on mobile browsers. The manual choice is not written to local storage and is re-evaluated against the system preference after a reload—this is deliberate: the site treats "follow the system" as the default experience and introduces no extra state persistence.

**Transition**: theme changes cross-fade over 0.5s through CSS custom properties, covering the background, cards, gradient text, glow, trail, fireworks and bottom stars.

**Color tokens**: all colors are centralized in two sets of custom properties, `:root` and `[data-theme="dark"]`, covering the background (light `#E8EEFA` / dark `#0E0E13`), cards, primary text, secondary text, accent (light `#4A6CF7` / dark `#6361DC`), card glow, border gradients, dot matrix and footer colors. No hard-coded color values exist in the page, so a new element needs only to reference the variables to adapt to both themes automatically.

### 3.2 Device Adaptation and Greeting

**Thresholds**:

| Device type | Condition | Displayed copy |
| --- | --- | --- |
| Phone | Viewport width < 768px | Hi, I'm **Ntars** (personal mode) |
| Tablet | 768px ≤ viewport width ≤ 1180px and touch capability present | Studio mode in landscape, personal mode in portrait |
| Desktop | Everything else | Hi, We're **Ntarstudio** (studio mode) |

Tablet detection additionally requires `ontouchstart in window` or `navigator.maxTouchPoints > 0`, so that a desktop browser in a large window is not misclassified as a tablet. On tablets the page listens to `resize` and `orientationchange` (the latter is handled after a 200ms delay, waiting for the system to finish rotating) and switches mode automatically on rotation; because the mode is already determined by orientation, click-to-toggle is disabled on tablets, so that a manual state cannot overwrite the orientation decision.

**Toggle animation**: `fade-out` is added first (300ms), the copy is replaced when the animation ends, then `fade-in` is added (300ms); during this an `isAnimating` flag prevents rapid clicks from corrupting the state.

**Typewriter effect**: driven by Typed.js, looping two lines of copy, `>_ Remember what is important` and `>_ Forget what is painful`, with the parameters `typeSpeed: 50`, `backSpeed: 20`, `startDelay: 300`, `loop: true`, `showCursor: false`. Turning the cursor off is deliberate: the page already has background particles and a pointer trail, and a blinking cursor on top of them would break the overall sense of calm.

### 3.3 Project Cards

**Layout**: `.link-card-list` uses `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))` with a 16px gap and a maximum width of 968px, centered on the page. The two cards form two equal columns on desktop and drop automatically to one column on narrow screens, with no extra media queries.

**Glow interaction**: on `mousemove`, `app.min.js` reads the pointer coordinates relative to the card and writes them into the two CSS variables `--mouse-x` / `--mouse-y`; the card's `::before` draws the follow glow with `radial-gradient(400px circle at var(--mouse-x) var(--mouse-y), ...)`, and the `.show` layer draws the hover fill. When the pointer leaves the card area, the opacity of `.show` is set to 0, so that no glow lingers at the card edges. This implementation adds no extra DOM structure and triggers no layout reflow.

**Structural consistency**: the two cards use the same DOM structure and arrow icon (inline SVG, colored with `currentColor`); only the copy, links and an optional icon differ — the Ondra card places a 40×40 project icon `assets/img/dpet-icon.svg` (taken from the in-house NT-Dpet site icon, natively supported by the `.link-card-item img` rule) before the arrow. The purpose is to ensure that a status change on any one card cannot cause a layout difference.

**Accessibility**: the outer element of each card is an `<a>`; when opening in a new window it always carries `rel="noopener noreferrer"`, preventing the target page from controlling this page back through `window.opener`.

### 3.4 Contact Modal

**Entry point**: the fixed text button `#contact-card` in the top-right corner, with `position: fixed`, `role="button"`, `tabindex="0"`, `aria-haspopup="dialog"` and `aria-controls`; it responds to mouse clicks and to the keyboard `Enter` / `Space`.

**Closing**: clicking the overlay, clicking the close button at the top-right of the panel, or pressing `Esc`—the three are equivalent.

**Scroll lock and offset compensation**: on open, the scrollbar width is computed as `window.innerWidth - document.documentElement.clientWidth` and applied to `body` as an equal `padding-right`, before `overflow: hidden` is set. Without this compensation, the disappearing scrollbar would shift the whole page to the right and cause a horizontal jump.

**Close sequence**: closing does not unlock scrolling immediately; it waits for the panel's `opacity` transition to end (listening to `transitionend`, with a 500ms timer as a fallback that covers the case where `prefers-reduced-motion` skips animations), then hides the container and restores scrolling. The exit animation transitions only `opacity` and does not involve `transform`; otherwise the panel would move toward its transform origin and look as if it were being "sucked" into the corner.

**Content grouping**: the social platforms (GitHub, Afdian, Bilibili) are external links that open in a new window; the contact details (email, QQ, WeChat) are plain text that copy to the clipboard on click.

**Clipboard implementation**: `security.js` intercepts `selectstart` and `copy` globally, and the plain-text items cannot be reached through an `<a>`; the copy feature therefore bypasses the event layer and writes directly with `navigator.clipboard.writeText()`. On success it shows "Copied", on failure "Copy failed", and it restores the original copy after 1.2s; during that feedback window the same item is de-duplicated through a `data-copied` marker, which prevents repeated clicks from stacking timers.

**Accessibility**: the panel is `role="dialog"` with `aria-modal="true"` and an `aria-labelledby` pointing at the heading; on open, focus moves to the close button, and on close it returns to the element that triggered the dialog; every interactive item supports keyboard operation.

### 3.5 Visual Effects

| Effect | File | Trigger | Theme adaptation |
| --- | --- | --- | --- |
| Firework particles | `firework.js` | Click / touch | Reads CSS variables to determine the particle color |
| Pointer trail | `trail.js` | Pointer movement | Dark trail on the light theme, light trail on the dark theme |
| Background particles | `bg.js` | Always on, repelled by the pointer | Node and link colors switch with the theme |
| Card glow | `app.min.js` | Card hover | Controlled by `--magical-glow` |
| Bottom decorations | `base.css` | Always on | Glow, three layers of rising stars (1px / 2px / 1px), earth circle |

Scripts load in dependency order: `security.js` → `app.min.js` → `anime.js` → `firework.js` → `trail.js` → `bg.js`. The fireworks rely on anime.js timeline capabilities and must therefore load after it; the security module has the highest priority and executes before the other scripts.

### 3.6 Security Hardening

`security.js` provides the following interception: it blocks text selection, copying and cutting; blocks the context menu and dragging; suppresses the shortcuts associated with developer tools and source viewing (F12, `Ctrl+Shift+I/C`, `Ctrl+U/S/P`, `Ctrl+A`); hides address hints when hovering links; monitors whether `body` has been emptied and reloads the page if so; and prints a notice in the console when developer tools are detected as open.

**Limits of these measures (important)**: the measures above only raise the bar for casual copying; they constitute no form of content protection or encryption whatsoever. Front-end code and page content are always visible to visitors, and no security script can change that. Information that must remain confidential must never be placed in the front end.

**Content Security Policy**: the page declares its resource allowlist through `<meta http-equiv="Content-Security-Policy">`. `default-src` and `script-src` allow only `'self'`, inline scripts and `https://unpkg.com`; `img-src` allows only `'self'` and `data:`; `frame-src` and `object-src` are `'none'`, forbidding embedded frames and plugins; `connect-src` is limited to `'self'`, and the page issues no external API requests. The page also declares `X-Content-Type-Options: nosniff`, `X-Frame-Options: DENY`, `X-XSS-Protection` and `referrer: no-referrer`, where `no-referrer` prevents the referrer address from leaking when a visitor navigates from this page to a third party.

### 3.7 PWA

**Manifest**: `manifest.json` declares `display: standalone`, `display_override: ["standalone", "minimal-ui"]`, `orientation: portrait-primary`, `lang: zh-CN` and the categories `lifestyle` / `utilities`, and provides icons in 192, 512 and SVG formats.

**Cache strategy**: `sw.js` uses "cache-first with background update". On a cache hit the response is returned immediately while a network request runs in the background and the new response is written back to the cache; on a miss the request goes to the network, and a successful response is written to the cache; if the network fails and the request is for HTML, it falls back to `index.html`, while other resources return 503.

**Cache discipline**: `CACHE_NAME` is currently `ntarstudio-v4`. Whenever any resource covered by the precache list changes (including Typed.js loaded through the CDN), this version number must be bumped at the same time, otherwise visitors will keep hitting the old cache. The `install` phase calls `skipWaiting()`, and the `activate` phase deletes all caches that are not the current version and calls `clients.claim()` to take over pages immediately.

**Installation**: the page listens to `beforeinstallprompt` and stores the event object; it currently relies on the browser's native install UI and provides no custom install button. `display-mode: standalone` is used to determine whether it is already running as an app.

### 3.8 SEO and Structured Data

| Item | Content |
| --- | --- |
| `description` | Covers the brand name and the positioning, status and domain of the two operating projects |
| `keywords` | Brand terms, project codes and product type terms; all terms of discontinued projects removed |
| Open Graph | `og:type` / `title` / `description` / `url` / `site_name` / `locale` |
| canonical | `https://www.ntars.cn/`, consistent with `og:url` |
| JSON-LD | Schema.org `Organization`, with `name`, `alternateName`, `url`, `description`, `sameAs` (GitHub, Bilibili, Afdian) |
| robots | `index, follow, noarchive, max-image-preview:large`; `noarchive` stops search engines from saving snapshots |
| Site verification | Baidu, verified both by `baidu_verify_codeva-C4tp7NQbk5.html` and by the `baidu-site-verification` meta tag |

The JSON-LD keeps only the organization-level `url` (the site itself); the two operating projects' official addresses are presented in the project cards and the status table. Ondra's official site `ai.ntars.cn` is now live and reachable by search engines through the card's direct link; `x.ntars.cn` is not live and therefore appears in no metadata.

### 3.9 Footer and ICP Filing

The footer sits after the page content and before the bottom decoration layer, and contains two lines: the ICP filing number (linking to `beian.miit.gov.cn`, opening in a new window) and the copyright line `© 2024 - 2026 Ntarstudio. All Rights Reserved.` The filing number uses its own style class and does not change meaning with the theme; only its color follows the theme.

---

## 4. Tech Stack and Open-Source Components

### 4.1 Technical Composition

| Layer | Choice | Notes |
| --- | --- | --- |
| Structure | Native HTML5 | Single file, semantic tags plus supplementary `role` attributes |
| Styling | Native CSS (custom properties + Grid + Flexbox) | No preprocessor in the build, no CSS framework |
| Interaction | Native JavaScript (mostly ES5 syntax) | No framework, no module bundling, loaded directly with `<script>` |
| Animation | anime.js v2.0.2 | Used only by the firework particles |
| Fonts | System font stack | No web fonts loaded |
| Icons | In-house SVG / PNG | No icon library |
| Offline | Service Worker + Web App Manifest | Cache-first strategy |
| Deployment | EdgeOne Pages | Static hosting, no server-side runtime; pushing to `main` triggers an automatic EdgeOne release — no GitHub Pages or Tencent Cloud COS |

The page uses no jQuery, Vue, React or any UI component library; no atomic CSS framework such as Tailwind; no build tool (Vite / Webpack / Rollup); and no npm dependencies. The repository therefore contains no `node_modules`, `package.json` or lock file.

### 4.2 Third-Party Components

The following is all third-party content actually used or distributed by the page. The complete copyright notices and redistribution obligations are in [`NOTICE`](NOTICE).

| # | Component | Version | Copyright holder | License | Integration | Purpose |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | asorn/asorn-open | — | asorn | Apache-2.0 | Source derivation | Initial base for the page structure and basic layout |
| 2 | anime.js | v2.0.2 | Julian Garnier (2017) | MIT | Whole file embedded at `assets/js/anime.js` | Timeline and easing for the firework particles |
| 3 | Typed.js | 2.0.16 | Matt Boldt (year as stated in the upstream LICENSE) | MIT | unpkg CDN + Service Worker precache | Typewriter effect in the greeting area |

**Note on derivation**: this project modifies, extends and redesigns the interface and structure of asorn/asorn-open, and is therefore a modified derivative work. In accordance with Section 4 of Apache-2.0, the original copyright notice, the full license text (`LICENSE-Apache-2.0.txt`) and a statement of changes (`NOTICE`) have been retained. In the `base.css` actually loaded by the page, the card glow (`.magical`) and some layout breakpoints come from upstream; the contact modal, the dual-theme tokens, the footer and the responsive details are new or rewritten by this project.

**License obligations**:

- **MIT (anime.js, Typed.js)**: the original copyright notice and license statement must be retained on distribution. The `anime.js` file header already retains the `Released under the MIT license` statement and it must not be removed; `Typed.js` is loaded from a CDN, and if it is ever embedded locally, its license text must be included as well.
- **Apache-2.0 (asorn/asorn-open)**: distributing a derivative work requires retaining the copyright notice and the full license text, and stating which files were modified. This project discharges that obligation through `NOTICE` and `LICENSE-Apache-2.0.txt`.

### 4.3 Not Used (Exclusions)

To avoid misunderstanding, the following are **not used by this project**:

| Item | Status |
| --- | --- |
| Third-party web fonts (Google Fonts etc.) | Not used. The font stack is system fonts, with no external font requests |
| Third-party icon libraries (Font Awesome, iconfont etc.) | Not used. The icons are in-house SVG / PNG |
| Front-end frameworks and UI component libraries | Not used |
| Analytics and tracking scripts (Google Analytics, Baidu Tongji etc.) | Not used |
| Advertising, comment and customer-service widgets | Not used |
| Cookie and local-storage writes | Not used (theme state is not persisted) |
| Back-end APIs and databases | Not used |

### 4.4 Trademark and Name Statement

The names and marks "Ntarstudio (星玖工作室)", "Ntarstudio", "Xael (玄玖灵犀)", "NT-Xhex", "Ondra (元鸣)", "NT-Dpet (玄宠)", "NT-Dpet", "NT-Sine (玄玖大模型)" and "NT-Sine" are owned by Ntarstudio. MIT and Apache-2.0 grant rights to code only: they grant no right to use the trademarks and no right to use them in a way that implies endorsement by the original authors.

Third-party names mentioned in the page and in this document (GitHub, Bilibili, Afdian, DeepSeek, Qwen and others) are owned by their respective rights holders and are used only to identify navigation targets or compatibility targets; no affiliation or endorsement is implied.

---

## 5. Copyright and Licensing

### 5.1 License of This Project

| Scope | License | Full text |
| --- | --- | --- |
| First-party code (page structure, styles, scripts and subsequent changes) | MIT | [`LICENSE`](LICENSE) |
| Portions derived from asorn/asorn-open | Apache License 2.0 | [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| Brand names, logo, interface design | All rights reserved | See `NOTICE` |

### 5.2 Redistribution Requirements

When redistributing this project, the following must be retained:

1. `NOTICE` (copyright and third-party notices);
2. `LICENSE` (full MIT text);
3. `LICENSE-Apache-2.0.txt` (full Apache-2.0 text);
4. the original copyright and license statements in the header of `assets/js/anime.js`;
5. the copyright notices for the upstream-derived styles in `assets/css/base.css` (already recorded in `NOTICE`).

The copyright and license statements of third-party files must not be removed or altered. Modified versions must not use the original project's brand marks and must not imply endorsement by the original authors.

---

## 6. Development and Operations

### 6.1 Local Run

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

Service Worker registers only under `localhost` or HTTPS; the `file://` protocol is not supported. The page has no build step, so a refresh after a change takes effect immediately.

### 6.2 Change Checklist

1. The titles, descriptions and links of the two cards match the real status of the operating projects;
2. `description`, `keywords`, `og:*`, JSON-LD and `canonical` match the wording of the page body;
3. When precached resources change, `CACHE_NAME` in `sw.js` has been bumped;
4. Both the light and the dark theme have been checked (double-click the heading to switch);
5. There is no text truncation or layout overflow at phone (< 768px), tablet (768–1180px) or desktop widths;
6. The background does not scroll while the modal is open, and the scroll position does not jump after it closes;
7. Any newly added third-party resource has its source, copyright holder, license and modifications recorded in `NOTICE` and in section 4.2 of this document.

### 6.3 Deployment

| Method | Status | Notes |
| --- | --- | --- |
| EdgeOne Pages | **Current production method (only)** | The main domain `www.ntars.cn` points to EdgeOne Pages; pushing to `main` publishes automatically. This project contains no workflow files and triggers no GitHub Actions |

### 6.4 Release Discipline

- After any change to the page content, the `sw.js` cache version must be checked in step, so that visitors do not stay on an old version for long;
- When the status of a sub-project changes (launch, shutdown, domain change), the two cards, the metadata and the status table in this document must all be updated together;
- Discontinued projects must never reappear in any form in the page, the keywords or the structured data;
- Before adding a third-party component, confirm that its license is compatible with Apache-2.0 / MIT, and register it in `NOTICE` before committing.

---

## 7. Changelog

| Date | Content |
| --- | --- |
| 2026-10-27 | Project framing updated: the three cards became two — Xael (玄玖灵犀, product live v4.3.0, official site `x.ntars.cn` not yet resolving, repository linked for now) and Ondra (元鸣, official site `ai.ntars.cn` live, software unreleased); the Ondra card uses the NT-Dpet icon asset (assets/img/dpet-icon.svg); the standalone NT-Sine card and the pet.ntars.cn link were removed as Ondra now covers them; meta, Open Graph and JSON-LD synchronized; cache version bumped to `ntarstudio-v6`; NOTICE trademark list, external links and asset registration updated |
| 2026-10-23 | Project information corrected: the three cards changed to NT-Xhex, NT-Dpet and NT-Sine; the discontinued NT-Know and NT-List removed; meta, Open Graph, JSON-LD and canonical synchronized; copyright and license statements for anime.js and Typed.js added to `NOTICE`; cache version bumped to `ntarstudio-v4`; deployment notes corrected against actual measurements (GitHub Pages not enabled) |
| 2026-10-20 | License change: first-party code switched to MIT, derived portions retain the full Apache-2.0 text and acknowledgements |
| 2026-10-20 | License compliance: `LICENSE` completed with the official full Apache-2.0 text; `NOTICE` added to record upstream provenance |
| 2026-10-15 | Icon replaced with a rounded-square "N+T" wordmark |
| 2026-10-15 | Initial commit: Ntarstudio official site homepage |

---

## Appendix: Contact

| Category | Name | Content |
| --- | --- | --- |
| Official website | Ntarstudio official site | https://www.ntars.cn/ |
| Social platform | GitHub | https://github.com/ntars |
| Social platform | Afdian | https://afdian.com/a/ntars |
| Social platform | Bilibili | https://space.bilibili.com/499925438 |
| Contact | Email | ntarsx@163.com |
| Contact | QQ | 3933361415 |
| Contact | WeChat | Ntarsv |
