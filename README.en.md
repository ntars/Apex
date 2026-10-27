[简体中文](README.md) | **English**

# Apex

The official site and project gateway of Ntarstudio (星玖工作室), codenamed Apex. One HTML file, one stylesheet, a handful of plain scripts — no framework, no build step, no backend.

| | |
|---|---|
| Code name | Apex |
| Live | <https://www.ntars.cn/> |
| Repository | <https://github.com/ntars/Apex> |
| Form | Single-page static site, installable as a PWA |
| Footprint | `index.html` + `assets/css/base.css` + 5 in-house scripts + 1 third-party animation library + `sw.js` |
| License | MIT for original code, Apache-2.0 for derived parts |
| ICP filing | 蜀ICP备2026027050号 |
| Copyright | Copyright (c) 2024–2026 星玖工作室 Ntarstudio |

## What this site is for

A visitor should immediately obtain three answers upon landing: who this is, what they build, and where to look.

So the site has exactly three jobs: **establish brand identity** (tie the three names — 星玖工作室, Ntarstudio, Ntars — together in the first screen), **route to the open-source projects** (two cards straight to the real destinations), and **state facts accurately** (nothing unreleased or retired appears in the page, its keywords or its structured data).

Its non-goals are as explicit: no accounts, no forms, no cookies, no analytics, no ads, no backend API. Everything is hard-coded in `index.html`; changing a sentence is one commit, with no CMS in between.

## Projects and how status is stated

| Project | What it is | Status | Where |
|---|---|---|---|
| **玄玖灵犀 Xael** | A local, offline library of traditional divination literature, with a same-named WeChat mini program and official account | Product live | [x.ntars.cn](https://x.ntars.cn/) |
| **元鸣 Ondra** | A one-click deployable, highly customizable AI companion | Product in closed beta | [ai.ntars.cn](https://ai.ntars.cn/) |

One rule governs every status label: **site status and product status are stated separately**. They are not equivalent — a running website does not mean an installable app, and a running app does not mean a reachable website.

- Xael: the product is live; the same-named WeChat mini program and official account are findable, with the official site `x.ntars.cn` as the single entry point;
- Ondra: the product is in closed beta; the official site `ai.ntars.cn` hosts the introduction and beta access, and the beta status is never folded into "live".

The status wording follows the up-to-date project descriptions above; the cards and metadata share this same framing, and any unreleased domain stays out of every metadata field.

## Page structure and code layout

Five blocks top to bottom: greeting, divider, projects, the fixed contact entry at top right, footer. Plus four persistent layers (firework canvas, trail canvas, background particle canvas, bottom decoration). No router, no virtual DOM, native scrolling.

```
Apex/
├── index.html                 # structure + metadata + four inline scripts
├── manifest.json              # PWA manifest
├── sw.js                      # Service Worker: pre-cache, cache-first, background refresh, old-cache cleanup
├── LICENSE                    # MIT text
├── LICENSE-Apache-2.0.txt     # Apache-2.0 text (the asorn-derived part)
├── NOTICE                     # copyright and third-party notices
├── 开源方案扫描.md             # open-source survey across the three projects
├── baidu_verify_codeva-C4tp7NQbk5.html   # Baidu site verification
├── tencent-cloud-config.yml   # Tencent Cloud hosting reference config (currently unused)
├── README.md / README.en.md
└── assets/
    ├── css/
    │   ├── base.css           # the only stylesheet loaded
    │   ├── base.scss          # source matching base.css
    │   └── base.min.css       # minified base.css
    ├── js/
    │   ├── security.js        # blocks selection/copy/context menu/shortcuts, tamper monitoring
    │   ├── app.min.js         # card glow: pointer coordinates → CSS variables
    │   ├── anime.js           # anime.js v2.0.2 (third-party, MIT, unmodified)
    │   ├── firework.js        # firework particles
    │   ├── trail.js           # pointer trail
    │   └── bg.js              # background particles and links
    └── img/                   # in-house N+T mark and PWA icons, including dpet-icon.svg
```

**Why six script files instead of one**: each file handles one concern and can be removed independently. When the trail effect is not needed, deleting the single `<script>` reference to `trail.js` leaves the other five unaffected. The only hard dependency between files is `firework.js` on `anime.js`, which fixes the load order at `security → app.min → anime → firework → trail → bg`.

**Why the cards are configuration-driven**: card content lives in a `PROJECTS` array inside `index.html` (title, description, link, optional icon), and the arrow SVG is defined once. Changing a project's status is one data line instead of a block of HTML — which is what prevents "updated the card, forgot the metadata" and "the two cards drifted apart in structure", both of which have happened here before.

## Implementation notes

### Theme: follow the system, allow manual override, forget it on reload

An inline script in `<head>` reads `prefers-color-scheme`; when the media query is unavailable it falls back to local time (light 6:00–18:00, dark otherwise) and writes the result to `<html data-theme>` plus `color-scheme`. Double-clicking the "星玖工作室出品" heading flips it manually and syncs `<meta name="theme-color">` so the mobile address bar matches.

The manual choice is deliberately not persisted in localStorage. Following the system is the default experience; storing a switch would add one more piece of state to explain. Reload returns to the system preference.

**No first-frame flash**: the script adds `theme-lock` to `<html>`, which suppresses every transition, and only removes it after two consecutive `requestAnimationFrame` callbacks. Without those two frames the browser paints once in its default colours and then jumps — a white flash on a dark system.

All colours live in two custom-property blocks (`:root` and `[data-theme="dark"]`); no hard-coded colour values in the page. New elements pick up both themes by referencing variables. Transitions are handled by one 0.5s rule under `html:not(.theme-lock)`.

### Greeting: three device classes, two voices

| Device | Rule | Shows |
|---|---|---|
| Phone | viewport < 768px | Hi, I'm **Ntars** |
| Tablet | 768–1180px with touch | studio mode in landscape, personal mode in portrait |
| Desktop | everything else | Hi, We're **Ntarstudio** |

Tablet detection additionally requires `ontouchstart in window` or `navigator.maxTouchPoints > 0`, otherwise a wide desktop window would be misread. On tablets the mode is decided by orientation, driven by `resize` and `orientationchange` (the latter delayed 200ms to let the rotation finish), so tap-to-toggle is disabled there — a manual state would fight the orientation state.

Switching runs `fade-out` (300ms), swaps the text, then `fade-in` (300ms), with an `isAnimating` flag blocking rapid taps.

Typing is Typed.js looping `>_ Remember what is important` and `>_ Forget what is painful`, with `typeSpeed: 50`, `backSpeed: 20`, `startDelay: 300`, `loop: true`, `showCursor: false`. Hiding the cursor is a deliberate choice: particles and a trail are already in motion, and an additional blinking cursor would break the overall calm.

### Project cards: a glow that follows the pointer

`.link-card-list` uses `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))` with a 16px gap, capped at 968px and centred. Two columns on desktop, one on narrow screens, no media query needed.

On `mousemove`, `app.min.js` computes the pointer position relative to the card and writes `--mouse-x` / `--mouse-y`; the card's `::before` draws the glow via `radial-gradient(400px circle at var(--mouse-x) var(--mouse-y), …)`. When the pointer leaves the card bounds the `.show` layer's opacity goes to zero so the glow does not linger on the edge. No DOM mutation, no layout thrash.

Both cards share an identical DOM shape; only text, link and optional icon differ — the Ondra card places a 40×40 `assets/img/dpet-icon.svg` before the arrow. The shared shape is what keeps a status change on one card from producing a layout difference.

Cards are `<a>` elements and every new-window link carries `rel="noopener noreferrer"`, so the target page cannot reach back through `window.opener`.

### Contact modal: two scrolling pitfalls

The entry is a fixed text button `#contact-card` at the top right (`role="button"`, `tabindex="0"`, `aria-haspopup="dialog"`, `aria-controls`) that responds to clicks and keys. It closes three equivalent ways: the overlay, the close button, `Esc`.

**Pitfall one — the page shifts when the scrollbar disappears.** On open it measures `window.innerWidth - document.documentElement.clientWidth`, adds that width to `body` as `padding-right`, then sets `overflow: hidden`. Without the compensation, the content behind shifts sideways as the scrollbar vanishes.

**Pitfall two — the exit animation pulls the panel toward its transform origin.** Closing does not unlock scrolling immediately; it waits for the panel's `opacity` transition to finish (`transitionend`, with a 500ms timer as a fallback for `prefers-reduced-motion`), then hides the container and restores scrolling. The exit transitions `opacity` only, never `transform`, otherwise the panel would travel toward its transform origin.

Content sits in two groups: social platforms (GitHub, afdian, bilibili) as outbound links, and contact details (email, QQ, WeChat) as plain text that copy on click. Copying bypasses the event layer and calls `navigator.clipboard.writeText()` directly, because `security.js` globally blocks `selectstart` and `copy`. Success shows "已复制", failure shows "复制失败", the original text returns after 1.2s, and a `data-copied` marker keeps repeated clicks from stacking timers.

### Visual effects and the security layer

| Effect | File | Trigger | Theme-aware |
|---|---|---|---|
| Fireworks | `firework.js` | click / touch | particle colours follow `data-theme` |
| Trail | `trail.js` | pointer movement | dark trail on light, light trail on dark |
| Background particles | `bg.js` | always, repelled by pointer | node and link colours follow the theme |
| Card glow | `app.min.js` | card hover | `--magical-glow` |
| Bottom decoration | `base.css` | always | glow + three drifting star layers + earth disc |

`security.js` blocks selection, copy, cut, the context menu, dragging, F12 and the view-source shortcuts, hides link URLs on hover, reloads when `body` is emptied, and prints a notice when DevTools is detected.

This needs saying plainly: **these measures only raise the bar for casual copying; they protect nothing.** Front-end code is always visible to the visitor and no script changes that. Do not put anything confidential in the front end.

The page declares its allowlist via `<meta http-equiv="Content-Security-Policy">`: `default-src` / `script-src` limited to `'self'`, inline scripts and `https://unpkg.com`; `img-src` to `'self'` and `data:`; `frame-src` / `object-src` to `'none'`; `connect-src` to `'self'` (the page makes no outbound API calls). It also sets `nosniff`, `X-Frame-Options: DENY` and `referrer: no-referrer`.

### PWA and cache discipline

`manifest.json` declares `display: standalone`, `display_override: ["standalone", "minimal-ui"]`, `orientation: portrait-primary`, `lang: zh-CN`, categories `lifestyle` / `utilities`, with 192, 512 and SVG icons.

`sw.js` runs cache-first with background refresh: a cache hit returns immediately while the network response is fetched and written back; a miss goes to the network; a failed navigation falls back to `index.html`, other assets return 503. `install` calls `skipWaiting()`, `activate` deletes non-current caches and calls `clients.claim()`.

**`CACHE_NAME` is currently `ntarstudio-v6`.** Change any pre-cached asset — including the CDN-loaded Typed.js — and the version must be bumped, or returning visitors stay pinned to the old cache. This is the easiest step to forget and the most visible when skipped.

### SEO and structured data

| Item | Content |
|---|---|
| `description` | brand name plus the positioning and status of both open-source projects |
| `keywords` | brand terms, code names, product categories; no retired projects |
| Open Graph | `type` / `title` / `description` / `url` / `site_name` / `locale` |
| canonical | `https://www.ntars.cn/`, matching `og:url` |
| JSON-LD | Schema.org `Organization`: `name`, `alternateName`, `url`, `description`, `sameAs` (GitHub, bilibili, afdian) |
| robots | `index, follow, noarchive, max-image-preview:large` |
| Verification | Baidu `baidu_verify_codeva-C4tp7NQbk5.html` plus a `baidu-site-verification` meta tag |

JSON-LD carries only the organisation-level `url`; project addresses are handled by direct card links, consistent with the current project status framing.

The footer holds two lines: the ICP filing number (linking to `beian.miit.gov.cn` in a new window) and `© 2024 - 2026 Ntarstudio. All Rights Reserved.`

## Stack

| Layer | Choice |
|---|---|
| Markup | Native HTML5, semantic tags plus `role` where needed |
| Styling | Native CSS: custom properties + Grid + Flexbox, no preprocessor in the build |
| Behaviour | Native JavaScript (mostly ES5 so older browsers run it directly) |
| Animation | anime.js v2.0.2, used only by the fireworks |
| Fonts | System stack, no web fonts |
| Icons | In-house SVG / PNG |
| Offline | Service Worker + Web App Manifest |
| Deployment | EdgeOne Pages |

No jQuery / Vue / React / UI kit, no Tailwind-style atomic CSS, no Vite / Webpack / Rollup, no npm dependencies — hence no `node_modules`, `package.json` or lock file in the repository.

### Third-party components

| Component | Version | Copyright | License | How it is included | Purpose |
|---|---|---|---|---|---|
| asorn/asorn-open | — | asorn | Apache-2.0 | source derivative | starting point |
| anime.js | v2.0.2 | Julian Garnier (2017) | MIT | whole file at `assets/js/anime.js` | fireworks timeline and easing |
| Typed.js | 2.0.16 | Matt Boldt | MIT | unpkg CDN + SW pre-cache | greeting typing effect |

**Derivative relationship**: this project was modified, extended and visually redesigned from asorn/asorn-open and is therefore a derivative work. Per Apache-2.0 section 4, the original copyright notice, the full license text (`LICENSE-Apache-2.0.txt`) and a statement of changes (`NOTICE`) are retained. In the current `base.css`, the `.magical` card glow and some layout breakpoints come from upstream; the contact modal, dual-theme tokens, footer and responsive details are new or rewritten here.

**MIT obligations**: keep the original copyright and license notices when redistributing. The `Released under the MIT license` header in `anime.js` must not be removed; Typed.js is loaded from a CDN and needs its license text attached if it is ever vendored locally.

### Explicitly not used

Third-party web fonts · third-party icon libraries · front-end frameworks and UI kits · analytics and tracking · ads, comments, support widgets · cookies and local storage writes · backend APIs and databases. None of the above.

### Names and trademarks

「星玖工作室」「Ntarstudio」「玄玖灵犀」「Xael」「NT-Xhex」「元鸣」「Ondra」「玄宠」「NT-Dpet」「玄玖大模型」「NT-Sine」 and their marks belong to Ntarstudio. MIT and Apache-2.0 grant rights to code only — not to trademarks, and not to imply endorsement. Third-party names appearing in this document (GitHub, bilibili, afdian, DeepSeek, Qwen, …) belong to their respective owners and are used only to describe link targets or compatibility.


## License and redistribution

| Scope | License |
|---|---|
| Original code (markup, styles, scripts and later changes) | MIT, see [`LICENSE`](LICENSE) |
| Portions derived from asorn/asorn-open | Apache-2.0, see [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| Brand names, logo, interface design | All rights reserved, see [`NOTICE`](NOTICE) |

Redistribution must keep `NOTICE`, `LICENSE`, `LICENSE-Apache-2.0.txt` and the copyright and license headers in `assets/js/anime.js`. Do not remove or alter third-party notices; modified versions must not use the original brand marks or imply endorsement.


## Running and deploying

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

No build step — edit and refresh. The Service Worker registers only on `localhost` or HTTPS; `file://` is unsupported.

**There is exactly one deployment path**: push to `main`, and EdgeOne Pages publishes automatically to the main domain `www.ntars.cn`. The repository contains no workflow files, triggers no GitHub Actions, and does not use Tencent Cloud COS.

### Checklist before committing

1. Both cards' titles, descriptions, links and statuses match reality, and no unreleased domain appears anywhere;
2. `description`, `keywords`, `og:*`, JSON-LD and `canonical` agree with the visible copy;
3. If a pre-cached asset changed, `CACHE_NAME` in `sw.js` was bumped;
4. Both themes were checked (double-click the heading to switch);
5. Phone (< 768px), tablet (768–1180px) and desktop widths show no truncation or overflow;
6. The modal locks background scrolling and the page position does not jump after closing;
7. Any new third-party asset is logged in `NOTICE` and in the table above with source, copyright holder, license and modifications.

### Release discipline

- Check `CACHE_NAME` after any content change — the step most often missed;
- When a project's status changes (live, retired, new domain), update the card, the metadata and this document together;
- A retired project must never return to the page, its keywords or its structured data;
- Confirm a new third-party component's license is MIT / Apache-2.0 compatible and log it in `NOTICE` before committing.

## Contact

| | |
|---|---|
| Website | <https://www.ntars.cn/> |
| GitHub | <https://github.com/ntars> |
| afdian | <https://afdian.com/a/ntars> |
| bilibili | <https://space.bilibili.com/499925438> |
| Email | ntarsx@163.com |
| QQ | 3933361415 |
| WeChat | Ntarsv |
