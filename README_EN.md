[简体中文](README.md) | **English** | [日本語](README_JA.md) | [한국어](README_KO.md) | [Français](README_FR.md) | [Русский](README_RU.md) | [Español](README_ES.md) | [العربية](README_AR.md)

# Apex

**The official site of Ntarstudio — and the index to fifteen projects.**

> **This repository has two roles**: it is the source of the studio's homepage (one HTML file, one stylesheet, a handful of plain scripts), and it is **the index to fifteen projects**. This document focuses on the latter: what each project is, how far it has got, and where to look. The site's own implementation is compressed into Chapter 5 and deliberately kept short.

![Status](https://img.shields.io/badge/status-online-2ea44f?style=flat-square)
[![GitHub license](https://img.shields.io/github/license/ntars/Apex?style=flat-square)](./LICENSE)
[![GitHub Star](https://img.shields.io/github/stars/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/stargazers)
[![GitHub Fork](https://img.shields.io/github/forks/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/network/members)
![GitHub Repo size](https://img.shields.io/github/repo-size/ntars/Apex?style=flat-square&color=3cb371)

[![Live](https://img.shields.io/badge/live-www.ntars.cn-0078d4.svg?style=flat-square)](https://www.ntars.cn/)
[![Projects](https://img.shields.io/badge/projects-15-8957e5.svg?style=flat-square)](#)
[![Build](https://img.shields.io/badge/build-none-2ea44f.svg?style=flat-square)](#)

---

## 1. Name and Positioning

> **仓库描述 / Description**：`星玖工作室官网与十五个开源项目总索引：一个 HTML、一份样式表、几个原生脚本 | The Ntarstudio official site and an index of fifteen open-source projects, in one HTML file and a stylesheet.`
>
> **话题标签 / Topics**（20 个，仅英文）：`frontend`, `landing-page`, `no-framework`, `personal-website`, `portfolio-site`, `pwa`, `service-worker`, `single-page`, `static-site`, `studio-website`, `vanilla-css`, `vanilla-javascript`, `ntarstudio`, `chinese-website`, `html`, `css`, `javascript`, `dark-mode`, `responsive-design`, `no-dependencies`


**Name**: Apex, meaning summit. As the studio's official site it plays the role of an entrance, not a product.

**One-line positioning**: a zero-dependency, zero-build single-page static site that states three things with the least possible code: who this is, what they build, where to look.

**Three boundaries**:

1. **It is a nameplate, not a showroom.** It carries no product features, no live demos, no embedded documentation. Visitors move on through direct links to each project.
2. **It is static files, not an application.** No backend, no database, no accounts. All content is hard-coded in `index.html`; changing one line of text is one commit.
3. **It is an index, not a content source.** A project's real information lives in its own repository and site. This page summarises and links; it does not duplicate.

**Why this README focuses on the projects**: the "星玖工作室出品" section on the homepage lists all fifteen projects. That list, Chapter 3 of this document, and the GitHub profile README are three renderings of one source. **Anyone who wants a quick picture of what the studio is building only needs this page** — no need to open fifteen repositories.

---

## 2. Overview

### 2.1 Background

Studio homepages usually fail in one of two ways. Either they become CMS-driven multi-page sites that go stale within six months, ending up older than the products; or they become showreels with the first screen buried in animation, leaving visitors unable to find the project links.

### 2.2 Problems addressed

A visitor should obtain three answers immediately on landing: **who this is, what they build, where to look**. If the page takes more than three seconds to answer, it has failed.

### 2.3 Core approach

The site has exactly three responsibilities:

| Responsibility | Approach |
|---|---|
| Establish brand identity | The first screen ties together 星玖工作室 / Ntarstudio / Ntars |
| Point to open-source projects | Six cards linking directly to the canonical addresses |
| State facts honestly | Unreleased and retired information never appears in the page, keywords or structured data |

### 2.4 Use cases

- The official nameplate page of a small independent studio;
- A static site that must stay stable and near-zero maintenance;
- A teaching sample of build-free front-end.

### 2.5 Non-goals

- No accounts, no forms, no cookies, no analytics, no advertising, no backend API;
- No jQuery / Vue / React / UI component library, no Tailwind, no Vite / Webpack / Rollup;
- No `localStorage` writes (the one exception is discussed in 5.1: theme state is deliberately not persisted).

---

## 3. Core Features

The homepage's "星玖工作室出品" section shows fifteen projects in a single Latin alphabetical order; each card states its own status, and the status wording is defined in 3.2.

**The fifteen projects are Amphoreus, Apex, Chiubay, Desop, Flutter-IDE, Gitrule-skill, NovaKit, Ondra, Relax, Serica, TapMC, Taycho-OS, Wacmin, Webroit and Xael.** GitHub hosts them and is not a project; the four directions inside Wacmin are an implementation detail and are not listed separately.

### 3.1 All projects (A–Z)

> The fifteen projects are listed in a single Latin alphabetical order, not grouped by status; a new project is inserted at its position, never appended. This list, the site `PROJECTS` array and the [ntars profile](https://github.com/ntars/ntars) stay identical. Status wording is defined in 3.2.

#### Amphoreus · In development

| | |
|---|---|
| What it is | A one-to-one recreation of the "Tarot Book" of Amphoreus from Honkai: Star Rail, built as a self-running simulated world: twelve Titans, thirteen Chrysos Heirs and twelve Kindling are computed from a seed, and the same seed always yields the same history |
| Stack | Python 3.11+ (standard library only) · SQLite · HTML / CSS / Vanilla JS |
| Status | In development: the simulator runs and `/book` works; official baseline screenshots are incomplete, so no pixel-level match is claimed |
| Platform | macOS / Linux / Windows (standard library only) |
| License | MIT |
| Repository | <https://github.com/ntars/Amphoreus> |

The same seed always yields the same history; a new seed yields a new Amphoreus. The rule engine decides *what happened*, and the local model only decides *how it is told*. At runtime the web page loads no bitmap or SVG; every shape is drawn with gradients, borders and `clip-path`.

**Why it is worth a look**: it turns both "deterministic narrative" and "zero-image UI" into checkable engineering constraints rather than a concept demo.

#### Apex · Live

| | |
|---|---|
| What it is | The site you are reading: the studio's nameplate and the index of all projects |
| Stack | HTML · CSS · Vanilla JS |
| License | MIT (Apache-2.0 for the rules derived from asorn/asorn-open, see [LICENSING.md](LICENSING.md)) |
| Entry | <https://www.ntars.cn/> |
| Repository | <https://github.com/ntars/Apex> |

One HTML file, one stylesheet, a handful of plain scripts. No framework, no build step, no backend. Zero dependencies means no toolchain can break it later.

**Why it is worth a look**: it is a sample of build-free front-end work — how one HTML file can organise a whole site without depending on a toolchain that will eventually be abandoned.

#### Chiubay (玖白) · Research prototype

| | |
|---|---|
| What it is | Growing an agent from scratch over the long term: personal AGI mechanism research built as six developmental loops |
| Stack | Python · NumPy (in-house tensors and hand-written backpropagation; no torch, JAX or pretrained weights) |
| Status | Research prototype: the in-house tensor stack and the E3 identity-loop experiment run; the other five loops remain on paper |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/Chiubay> |

The goal is not to ship human-level AGI but to turn "how an agent is raised into shape" into falsifiable mechanism experiments. Each report states only what was verified, never that AGI was achieved.

**Why it is worth a look**: it publishes the training rules, the evaluation protocol and the failure boundaries, and treats the compute gap as a physical limit rather than an optimisation problem.

#### Desop · Buildable MVP

| | |
|---|---|
| What it is | A macOS-style desktop suite for Windows: dock, top bar, desktop widgets and dynamic island |
| Stack | Python 3.10+ · PySide6 (user mode) |
| Version | `0.2.0` |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/Desop> |

No system modification, pure user-mode operation, and uninstalling restores the desktop. The four components share one set of design tokens and can be enabled individually. The performance budget is a release gate: idle CPU < 1%, memory < 150 MB, dock magnification ≥ 55 fps; if it is missed, it does not ship.

**Why it is worth a look**: it answers the common complaint that beautification tools slow the machine with hard numbers instead of "we will optimise later".

#### Flutter-IDE · Available, 0.2.0

| | |
|---|---|
| What it is | A source-first visual IDE for Flutter: drag widgets on a canvas, edit values in a property panel, and keep Dart code that can be maintained without the tool |
| Stack | Dart 3.14+ · Flutter Desktop |
| Version | `0.2.0` |
| Status | Available: CLI validation and code generation, desktop file tree and multi-tab editing, canvas drag, property editing, VM point-and-select and hot reload, distributable macOS DMG/ZIP |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/Flutter-IDE> |

The only test of whether the project should exist: delete the IDE and see whether the project still runs `flutter run`. Intent outlines, overlays and design tokens are therefore plain files committed to git; no project structure lives only inside the tool.

**Why it is worth a look**: "not locked into a tool" is written as three acceptance criteria — no private schema, one change yields one diff, the same input generates the same output twice — rather than a slogan.

#### Gitrule-skill · Delivered

| | |
|---|---|
| What it is | A general specification set covering the project lifecycle: planning, requirements, architecture, development, testing, deployment, operations and iteration, plus documentation, compliance and programmatic access for AI agents |
| Stack | Markdown (zero third-party dependencies) · Python CLI · MCP server |
| Scope | 68 specifications × 12 languages, with the same identifiers mapped one-to-one across language directories |
| Status | Delivered: the CLI reports 0 issues; the Skill, the expert pack and the MCP server are all available |
| License | MIT |
| Repository | <https://github.com/ntars/Gitrule-skill> |

One specification per file, independent and read on demand. A zero-dependency CLI checks broken links, orphan files, responsibility sentences, code fences, index counts and placeholder registration; `optimize` applies only fixes that are safe to automate.

**Why it is worth a look**: it turns conventions — which 20 chapters a README needs, how a repository is named, how the description and topics are set — into checkable files and commands. The documentation alignment of the fifteen repositories used it as the single baseline.

#### NovaKit · Skeleton stage

| | |
|---|---|
| What it is | The first batch of utilities for a newly installed computer: file, image, text and system tools in one offline suite, with no network and no account |
| Stack | Rust (edition 2024) · Tauri 2 |
| Status | Skeleton stage: the project and the list of 36 tools are fixed, business code is being written, no release |
| Platform | macOS first; Windows / Linux planned |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/NovaKit> |

Tools are organised in four tiers — pure Rust, system capability, external component and process plugin — each with its own implementation and acceptance method. Plugins speak JSON-RPC 2.0 over stdio, and every permission is denied by default.

**Why it is worth a look**: it derives the tool list from "what is needed in the first week after installing an OS" and fixes the security boundary by tier instead of growing into an all-in-one suite.

#### Ondra (空谷) · Internal beta, 3.0.0-alpha.22

| | |
|---|---|
| What it is | A plugin-first desktop AI companion: the interface reads only plugin projections; emotion, memory and context are the three core mechanisms; all data stays on the local machine |
| Stack | Flutter (desktop and web) · Cordis 4.1.0 (plugin framework) · dsh kernel (Node) |
| Version | Beta `3.0.0-alpha.22` |
| Platforms | macOS runs; Windows has a release bundle; the Android kernel boots on a device (real-device handshake pending); web builds; iOS / OHOS have generated projects only |
| License | Apache-2.0 / MIT |
| Entry | <https://ai.ntars.cn/> |
| Repository | <https://github.com/ntars/Ondra> |

Three core mechanisms: emotion (a state variable with inertia), memory (an eleven-link chain) and context (frozen prefix + incremental injection + budget packing). The plugin page merges 18 bundled entries with 75 from the assembly layer into 93 entries, each of which can be toggled.

**Why it is worth a look**: it breaks companionship into mechanisms that can be engineered separately, and a boot-order patch took the silent degradation of 18 plugins caused by concurrent `apply` calls from 55 entries to zero. Only one projection layer sits between the interface and the plugins, so pages never hold plugin internals.

#### Relax (悠然) · Early development

| | |
|---|---|
| What it is | A self-hosted family platform for chat, calendar, files and photos: one single-process server, Android clients, and data that never leaves the house |
| Stack | Rust · Tauri 2 · axum · SQLite · React + TypeScript |
| Status | Early development: the server route skeletons for authentication, sync, chat, announcements, calendar and files are in place; the business loop is unfinished |
| Platform | Server on macOS / Linux; client on Android API 24+ |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/Relax> |

All business logic lives in Rust: the front end only renders and calls `invoke()`; it never makes network requests, never connects to SQLite directly and never persists a token. Messages enter an outbox and are submitted idempotently by `opId` after recovery.

**Why it is worth a look**: it turns "data autonomy" into five machine-checkable architectural locks rather than a privacy slogan.

#### Serica (行简) · Specification frozen, implementation stops at the lexer

| | |
|---|---|
| What it is | A programming language for multi-device sync applications: Chinese throughout, `.serica` sources, the `serica` command, native executables as output |
| Stack | Go (seed compiler stage0) · self-hosting path · writes Mach-O directly |
| Version | Specification v3.1 is frozen; the seed implementation stops at lexing and `check`: IR generation (M3) and code generation (M4) are unimplemented, so no executable can be produced yet |
| Scope | 1,928 seed lines against a 5,000-line cap, with per-line attribution; the seed directory is deleted after self-hosting |
| License | Apache-2.0 |
| Platform | Verified on macOS arm64 only |
| Repository | <https://github.com/ntars/Serica> |

The seed compiler is designed to emit no C and to call neither LLVM nor an assembler or linker: it writes Mach-O itself. Chinese punctuation is grammar at the lexical layer rather than typography, and diagnostics report both the code-point column and the display column (`line 3, column 38 (display cell 55)`). **These are design targets, not current capability**: all that runs in the repository is the lexer and the `check` command; `ir` returns "IR generator not implemented (M3)" and `build` returns "code generator not implemented (M4)", so no executable can be produced yet, and it **cannot be used for production software**.

**Why it is worth a look**: it turns "Chinese is not just translated keywords" into checkable engineering constraints — a 5,000-line seed cap, a per-line attribution table, deleting the seed after self-hosting, and an output type that a single `file` command will verify — rather than a document of pure vision.

#### TapMC · Skeleton stage, 0.1.0

| | |
|---|---|
| What it is | A Minecraft Java Edition launcher covering seven platforms: instances, mods and Java runtimes are managed separately, and the interface and process layer communicate through one JSON-RPC contract |
| Stack | Flutter (interface) · Rust + eframe (native shell) · Java 21 (server side) |
| Status | Skeleton stage: the path works; 84 Java tests and 21 Dart cases pass; no release |
| Platform | Web and Android build; the other five targets are unverified |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/TapMC> |

The back end is the single source of truth, and the front end only renders and collects input. Instances, mods and Java runtimes are managed separately; the interface and the native shell share one JSON-RPC contract. The repository still contains the code and documents of an early sandbox server alongside the launcher line, and they have not been cleaned up.

**Why it is worth a look**: it keeps the business logic shared by seven platforms on the interface side and gives Java detection and process control to the Rust shell, so the interface can change without touching process management. Unfinished capabilities (Modrinth access, dependency resolution, multiple Java versions) are listed one by one under known limitations instead of being counted as done.

#### Taycho-OS (太初) · Design stage (placeholder)

| | |
|---|---|
| What it is | A native system written from scratch in Serica: execution model, capability boundary, message mechanism, windows and text all rebuilt |
| Stack | Serica (planned) · native executables |
| Status | Design stage: only design documents and a placeholder repository; no code yet |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/Taycho-OS> |

No existing kernel, runtime or graphics stack is reused; every IO and system access must declare a capability, and anything undeclared is refused.

**Why it is worth a look**: it states "from scratch" as machine-checkable boundary conditions rather than a manifesto.

#### Wacmin · Available (three releasable, AppOnWin experimental)

| | |
|---|---|
| What it is | A bidirectional interoperability suite between macOS and Windows, with an AI access layer |
| Stack | Node.js · Python · Rust |
| Status | Three directions releasable (Mac2Win / ExeOnMac / Win2Mac); AppOnWin is experimental and unverified because the local environment cannot support it |
| License | Apache-2.0 / MIT |
| Repository | <https://github.com/ntars/Wacmin> |

Four directions are formed by crossing two hosts with two actions; the first three are releasable and the fourth remains experimental:

| Order | Direction | Host action | Tests |
|---|---|---|---|
| 1 | **Mac2Win** | Build a Windows installer on a Mac | 125 |
| 2 | **ExeOnMac** | Run a Windows program on a Mac | 319 |
| 3 | **Win2Mac** | Build a macOS app bundle on Windows | 121 |
| 4 | **AppOnWin** | Run a macOS program on Windows | Experimental, unverified |

**Plus an `ai/` access layer**: one scheduling layer exposed in four forms — an MCP server (for Claude Desktop, WorkBuddy and Cline), a unified CLI, a Skill and an expert pack. The protocol and transport layers total under 900 lines with zero third-party dependencies; the official SDK was not used.

**Why it is worth a look**: it orders development by certainty, leaves the most likely failure for last and defines the degradation path in advance — even if the last direction fails, the first three still stand. That direction has not produced a reproducible verification result, so it is labelled experimental and does not count as available. The `ai/` layer was not bolted on as an MCP wrapper: it emerged after the scheduling logic was extracted from the shell into `directions.mjs`, and the extraction exposed a dormant defect — `/api/status` wrote 21 lines of Chinese usage text to stdout on every request and set `exitCode` to 2, which the console never noticed because it never reads its own stdout, but which is fatal under the MCP rule that stdout carries protocol messages only.

#### Webroit · Live

| | |
|---|---|
| What it is | An Android toolbox in the browser: ADB and Fastboot over WebUSB, with 61 features implemented and 152 planned |
| Stack | TypeScript · Vite · WebUSB · ya-webadb |
| Form | A pure static site: no backend, no installation, no drivers |
| License | Apache-2.0 / MIT |
| Entry | <https://adb.ntars.cn/> |
| Repository | <https://github.com/ntars/Webroit> |

Everything needed for Android tinkering is moved into the browser. The ADB protocol is implemented on top of Tango; what is delivered is the interface and the workflows a user actually needs — app management, file browsing, terminal, screen mirroring, logs and flashing — 61 implemented and 152 planned, each carrying a risk tier.

**Why it is worth a look**: it removes the entire "environment setup" layer. The usual path is download Platform-Tools → configure PATH → install a USB driver → write udev rules → connect → type commands; Webroit compresses the first five steps into "open the page → click connect → click a feature". The real difficulty was never typing commands, but the moment after setup when the device still will not connect and you cannot tell whether it is the cable, the port, the driver, or an `adb.exe` still holding the interface.

**Two further points**: the whole product is a static `dist/`, and `grep -r "http" dist/` finds no backend address of its own — "data never leaves this machine" is a verifiable fact, not a promise. Every operation is also graded by risk, so a command copied from elsewhere states what it will change and whether it can be undone.

#### Xael (玄玖灵犀) · Live

| | |
|---|---|
| What it is | A local, offline corpus of Chinese calendrics and mantic literature: 22 features computed from first principles, with no lookup tables and no network |
| Stack | JavaScript (zero dependencies) · PWA · WeChat Mini Program · uni-app |
| Version | `5.0.0` |
| License | Apache-2.0 / MIT |
| Entry | <https://x.ntars.cn/> |
| Repository | <https://github.com/ntars/Xael> |

It covers Four Pillars, Zi Wei Dou Shu, Qi Men Dun Jia, Da Liu Ren, Liu Yao, Mei Hua Yi Shu, Xuan Kong Flying Stars and almanac date selection. The calendar foundation derives new moons from astronomical series in real time instead of relying on a table; twenty public-domain classics serve as base texts, each rule corrected item by item with its evidence tier stated. The WeChat Mini Program and the official account are searchable under the same name.

**Why it is worth a look**: it follows "compute it instead of looking it up" to the end, and annotates every conclusion with its textual basis and its points of uncertainty.

### 3.2 Status wording

**Site status and product status are not equivalent**: a running site does not mean installable software, and running software does not mean the site is up.

| Project | Status | Meaning |
|---|---|---|
| Apex | Live | The site runs and the source is public |
| Gitrule-skill | Delivered | 68 specifications × 12 languages, CLI reports 0 issues; no versioned release, delivered from the main branch |
| Ondra | Internal beta | `3.0.0-alpha.22`: macOS runs, Windows has a release bundle, the Android kernel boots on a device (real-device handshake pending), web builds |
| Wacmin | Available | Mac2Win / ExeOnMac / Win2Mac are releasable, with CLI and MCP access; AppOnWin is experimental and does not count as available |
| Webroit | Live | The static site runs at `adb.ntars.cn`, 61 features are usable, the source is public |
| Xael | Live | A stable version (`5.0.0`) exists and is usable |
| Amphoreus | In development | The simulator and the book run locally; official baselines are incomplete; no pixel-level claim |
| Flutter-IDE | Available | `0.2.0`: desktop editing, canvas drag, property panel and macOS distribution are usable |
| NovaKit | Skeleton stage | The Tauri 2 project and the 36-tool list are in place; business code has not started |
| Chiubay | Research prototype | The in-house tensor stack and the E3 identity-loop experiment run; the other five loops remain on paper |
| Taycho-OS | Design stage | Design documents and a placeholder repository only; no code |
| Relax | Early development | Server route skeletons are in place; the business loop is unfinished; no APK |
| Serica | Specification frozen | Specification v3.1 is frozen; the seed implementation stops at lexing and checking, IR and code generation are unimplemented; no release and not usable for production software |
| TapMC | Skeleton stage | The path works; 84 Java tests and 21 Dart cases pass; no release |
| Desop | Buildable MVP | `0.2.0`: the Python + PySide6 user-mode implementation builds and runs, 77 tests pass, Windows 11 VM acceptance 8/8 PASS; desktop widgets have configuration only and no UI, physical-machine acceptance is outstanding |

**Why projects in the design stage still appear on the site**: the site is the studio's nameplate and shows what is being built, not only what has been finished. Stating the status clearly is enough: a visitor who reads "Design stage" or "Skeleton stage" knows there is nothing to download, which is more honest than hiding the project.

---

## 4. Core Characteristics

### Highlight 1: Fifteen projects on one page, three sources in step

- **Name**: Single-page index.
- **Value**: Solves "to learn what this studio builds you must open fifteen repositories".
- **Implementation**: The homepage cards, Chapter 3 of this document and the GitHub profile README list the same set with consistent status wording.
- **Differentiation**: Most personal pages list released projects only, or scatter the information across repository READMEs.
- **Evidence**: The three lists match item by item; see the status table in 3.2.

### Highlight 2: Zero dependencies, zero build, edit and refresh

- **Name**: No toolchain.
- **Value**: Solves "it stops building after six months without changes".
- **Implementation**: No `node_modules`, no `package.json`, no lockfile. `python3 -m http.server 8000` previews it locally.
- **Differentiation**: Most "minimal sites" still use Vite or Webpack on the grounds that "the template has it anyway".
- **Evidence**: No `package.json` at the repository root; deployment is "push main → EdgeOne Pages auto-publishes".

### Highlight 3: Theme follows the system, no white flash on first frame

- **Name**: Two-frame-locked initial theme.
- **Value**: Solves the white flash when opening the page on a dark system.
- **Implementation**: A synchronous inline script in `<head>` reads `prefers-color-scheme` and writes the result into `<html data-theme>`; it first adds `theme-lock` to suppress transitions, then removes it after two consecutive `requestAnimationFrame` frames once the theme settles.
- **Differentiation**: Common practice sets the theme on `DOMContentLoaded`, or does nothing to prevent the flash.
- **Evidence**: A unified 0.5 s transition rule under `html:not(.theme-lock)`.

### Highlight 4: Card glow follows the pointer without touching the DOM

- **Name**: Pointer glow driven by CSS variables.
- **Value**: Solves "hover effects causing layout thrash".
- **Implementation**: `app.min.js` computes the pointer's coordinates relative to the card and writes them to `--mouse-x` / `--mouse-y`; the card's `::before` paints the glow with `radial-gradient`.
- **Differentiation**: The common approach moves an absolutely positioned element on every `mousemove`, forcing compositing and reflow.
- **Evidence**: `app.min.js` only computes coordinates and writes variables.

### Highlight 5: Both dialog scrolling pitfalls handled

- **Name**: Scrollbar compensation and exit direction.
- **Value**: Solves two mistakes almost every hand-built dialog makes — the page shifting right when it opens, and the panel being "sucked" into a corner when it closes.
- **Implementation**: On open, add `padding-right` before setting `overflow: hidden`; on close, wait for the `opacity` transition to end (with a 500 ms fallback timer) before restoring scrolling, transitioning `opacity` only and never `transform`.
- **Differentiation**: Touching `transform` moves the panel toward the transform origin, which reads as being snapped into place.
- **Evidence**: Under `prefers-reduced-motion` the animation is skipped, and the 500 ms timer is the only path that still closes the dialog.

---

## 5. Design Details and Engineering Trade-offs

**This is the only chapter about the site itself.** It is deliberately compressed — the projects are the point.

### 5.1 Theme: follows the system, manually overridable, not remembered across reloads

Double-clicking 「星玖工作室出品」 flips the theme manually and syncs `<meta name="theme-color">` so the mobile address bar matches.

**Manual state is deliberately not written to `localStorage`.** The default follows the system; every stored switch is one more state to explain. A reload returns to the system preference.

### 5.2 Five page blocks

Top to bottom: greeting, divider, project section, contact entry at the top right, footer. Plus four persistent overlay layers (firework canvas, trail canvas, background particle canvas, bottom decoration).

No router, no virtual DOM; scrolling is native.

### 5.3 Three device bands in the greeting

| Device | Detection | Display |
|---|---|---|
| Phone | Viewport < 768 px | Hi, I'm **Ntars** |
| Tablet | 768–1180 px with touch | Studio mode in landscape, personal mode in portrait |
| Desktop | Everything else | Hi, We're **Ntarstudio** |

Tablet detection additionally requires `ontouchstart in window` or `navigator.maxTouchPoints > 0`, otherwise a large desktop window would be misdetected.

### 5.4 Project cards: configuration-driven

Cards render from the `PROJECTS` array, each entry holding title, description, link and an optional icon. `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))` with a 16 px gap gives three columns on desktop and one on narrow screens, with no media query.

Changing a project's status is changing one line of data, not a block of HTML — avoiding "changed the card but forgot the metadata" and "cards drifting structurally".

### 5.5 Six scripts rather than one

| File | Responsibility |
|---|---|
| `security.js` | Disables selection/copy/right-click/shortcuts; tamper detection |
| `app.min.js` | Card glow: pointer coordinates → CSS variables |
| `anime.js` | anime.js v2.0.2 (third-party, MIT, unmodified) |
| `firework.js` | Firework particles |
| `trail.js` | Pointer trail |
| `bg.js` | Background particles and links |

Each file does one thing and can be removed alone. The only hard dependency is `firework.js` on `anime.js`, so the load order is fixed: `security → app.min → anime → firework → trail → bg`.

### 5.6 The cache version number is the easiest step to forget

**`CACHE_NAME` is currently `ntarstudio-v12`.** Changing anything in the pre-cache list — including Typed.js from CDN — requires bumping the version, or returning visitors stay on the old cache.

### 5.7 The honest limits of the security measures

`security.js` intercepts selection, copy, cut, right-click, drag, F12 and view-source shortcuts.

**To be clear: these measures only raise the bar for casual copying; they provide no content protection whatsoever.** Front-end code is always visible to visitors.

### 5.8 CSP allowlist

| Directive | Value |
|---|---|
| `default-src` / `script-src` | `'self'`, inline, `https://unpkg.com` |
| `img-src` | `'self'` and `data:` |
| `frame-src` / `object-src` | `'none'` |
| `connect-src` | `'self'` (the page makes no external API requests) |

Plus `nosniff`, `X-Frame-Options: DENY` and `referrer: no-referrer`.

### 5.9 The three-place discipline

When a project's status changes (release, retirement, domain change), these three must be updated together:

1. The `PROJECTS` array in `index.html`;
2. Chapter 3 of this document;
3. The project table in the GitHub profile README `ntars/ntars`.

**Retired projects never return in any form** — not in the page, keywords or structured data.

---

## 6. Technology Stack and Dependencies

### 6.1 Stack

| Layer | Choice |
|---|---|
| Structure | Native HTML5, semantic tags plus `role` supplementation |
| Styling | Native CSS: custom properties + Grid + Flexbox |
| Interaction | Native JavaScript (mostly ES5 syntax) |
| Animation | anime.js v2.0.2, used only for firework particles |
| Fonts | System font stack; no web fonts |
| Offline | Service Worker + Web App Manifest |
| Deployment | EdgeOne Pages |

### 6.2 Third-party components

| Component | Version | Copyright holder | License | How included | Purpose |
|---|---|---|---|---|---|
| asorn/asorn-open | — | asorn | Apache-2.0 | Source derivation | Initial foundation |
| anime.js | v2.0.2 | Julian Garnier (2017) | MIT | Whole file embedded | Firework timeline and easing |
| Typed.js | 2.0.16 | Matt Boldt | MIT | unpkg CDN + SW pre-cache | Greeting typing effect |

**Derivation**: this project modifies, extends and redesigns the interface and structure on top of asorn/asorn-open, making it a derivative work. Under Apache-2.0 clause 4, the original copyright notice, the full licence text and a change statement are retained.

### 6.3 Explicitly not used

Third-party web fonts · third-party icon libraries · front-end frameworks and UI libraries · analytics and tracking · advertising and comment/support widgets · cookies and local-storage writes · backend APIs and databases.

### 6.4 Indirect dependencies

None. No transitive dependencies exist.

---

## 7. Installation and Deployment

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

No build step; edit and refresh. The Service Worker registers only on `localhost` or HTTPS — `file://` is not supported.

**There is exactly one deployment path**: push `main` → EdgeOne Pages publishes automatically, with `www.ntars.cn` pointing at the site. The repository contains no workflow files.

---

## 8. Quick Start

### 8.1 To read about the projects

Read Chapter 3 above, or visit <https://www.ntars.cn/>.

### 8.2 To run the site locally

1. `git clone https://github.com/ntars/Apex.git`
2. `cd Apex && python3 -m http.server 8000`
3. Open `http://localhost:8000`
4. Double-click 「星玖工作室出品」 to verify theme switching
5. Narrow the window below 768 px to verify the phone-mode copy
6. Click "Contact" at the top right to verify the dialog

---

## 9. Configuration

There is no configuration file. Everything adjustable sits in three places:

| Content | Location | What to change |
|---|---|---|
| Project cards | the `PROJECTS` array in `index.html` | Title, description, link, optional icon |
| Theme colours | `:root` and `[data-theme="dark"]` in `assets/css/base.css` | CSS custom properties |
| Cache version | `CACHE_NAME` in `sw.js` | Must be bumped whenever pre-cached assets change |

---

## 10. API and Module Reference

There is no API. Script responsibilities are in 5.5. Load order is fixed: `security → app.min → anime → firework → trail → bg`.

---

## 11. Repository Layout

```
Apex/
├── index.html                 # Structure + metadata + four inline scripts
├── manifest.json              # PWA manifest
├── sw.js                      # Service Worker
├── LICENSE                    # Full MIT text
├── LICENSE-Apache-2.0.txt     # Full Apache-2.0 text (asorn-derived parts)
├── NOTICE                     # Copyright and third-party statements
├── README.md / README_EN.md
└── assets/
    ├── css/
    │   ├── base.css           # The only stylesheet loaded
    │   ├── base.scss          # Style source corresponding to base.css
    │   └── base.min.css       # Minified build
    ├── js/
    │   ├── security.js
    │   ├── app.min.js
    │   ├── anime.js           # Third-party, MIT
    │   ├── firework.js
    │   ├── trail.js
    │   └── bg.js
    └── img/                   # In-house N+T wordmark and PWA icons
```

---

## 12. Performance

| Metric | Value | Notes |
|---|---|---|
| Build steps | 0 | No bundling, no minification pipeline |
| First-screen external requests | 1 | Typed.js (unpkg CDN, pre-cached) |
| Web fonts | 0 | System font stack |
| Layout reflows | 0 | The glow only writes CSS variables |
| Repeat visits | Served from cache | Service Worker, cache first |

---

## 13. Security and Privacy

| Dimension | Approach |
|---|---|
| Cookies | Not used |
| Local storage | No writes (manual theme state is deliberately not persisted) |
| Analytics | None |
| Third-party requests | Typed.js only (unpkg CDN) |
| CSP | Declared allowlist; `object-src` / `frame-src` set to `'none'` |
| Clickjacking | `X-Frame-Options: DENY` |
| Referrer leakage | `referrer: no-referrer` |

**An honest note on front-end content protection**: `security.js` only raises the bar for casual copying and provides no content protection.

---

## 14. Compatibility

| Environment | Status | Notes |
|---|---|---|
| Modern browsers | ✅ Full | Native CSS custom properties + Grid |
| Legacy browsers | ⚠️ Degraded | Scripts are mostly ES5; the theme does not apply but content remains readable |
| Phone (< 768 px) | ✅ | Full-width single column |
| Tablet (768–1180 px with touch) | ✅ | Dual mode by orientation |
| Desktop (≥ 1180 px) | ✅ | Three-column cards |
| Opened via `file://` | ⚠️ Partial | Service Worker does not register; everything else works |

---

## 15. Known Issues and Limitations

1. **The cache version depends on a human**: forgetting to bump `CACHE_NAME` leaves returning visitors on an old cache, with no error raised anywhere.
2. **Manual theme state is not persisted**: a reload returns to the system preference — by design.
3. **Tap-to-toggle is disabled on tablets**: the mode follows orientation.
4. **Front-end content protection does not work**: `security.js` only raises the bar.
5. **Typed.js comes from a CDN**: if unpkg is unreachable the typing effect fails, though the rest of the content is unaffected.
6. **Planned projects' cards have nothing to download**: the cost of labelling status honestly — and the reason nothing planned is described as built.

---

## 16. Changelog

The changelog lives on the **GitHub Releases** page: <https://github.com/ntars/Apex/releases>

The README describes the site's current state; releases record what changed each time. The two are never mixed.

---

## 17. Roadmap

1. **Automate the cache version**: replace the hand-written `CACHE_NAME` with a build-time asset hash.
2. **Card icons**: mount icons for all fifteen projects once available; all are currently `icon: null`.
3. **Accessibility audit**: `role`, `tabindex` and `aria-*` are present, but a full keyboard walkthrough and screen-reader test have not been done.
4. **Reduce third-party dependencies**: Typed.js is simple enough to replace with roughly 40 lines of native code.
5. **Open Graph preview image**: there is currently no `og:image`.

---

## 18. Contributing

### 18.1 Self-check before changing anything

1. All fifteen cards' titles, descriptions and links match the projects' real status;
2. `description`, `keywords`, `og:*`, JSON-LD and `canonical` stay in sync with the body copy;
3. If any pre-cached asset changed, `CACHE_NAME` has been bumped;
4. Both light and dark themes have been reviewed;
5. No truncation or overflow at phone, tablet and desktop widths;
6. The background does not scroll while the dialog is open, and scroll position does not jump after closing;
7. **A status change is edited in three places** (`PROJECTS` array, Chapter 3 of this document, GitHub profile README).

### 18.2 Release discipline

- Check `CACHE_NAME` after every content change;
- When a project's status changes, update the card, the metadata and the status table together;
- Retired projects must never return to the page, keywords or structured data;
- Confirm licence compatibility before adding a third-party component, and register it in `NOTICE` before committing.

### 18.3 Contact

| Channel | Address |
|---|---|
| Website | <https://www.ntars.cn/> |
| GitHub | <https://github.com/ntars> |
| Profile README | <https://github.com/ntars/ntars> |
| Email | <ntars@qq.com> · <ntarsx@163.com> |

---

## 19. Copyright and License

| Scope | License |
|---|---|
| Original code (structure, styles, scripts and subsequent changes) | MIT, see [`LICENSE`](LICENSE) |
| Parts derived from asorn/asorn-open | Apache-2.0, see [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| Brand names, logo, interface design | All rights reserved, see [`NOTICE`](NOTICE) |

Redistribution must retain `NOTICE`, `LICENSE`, `LICENSE-Apache-2.0.txt` and the copyright and licence headers in `assets/js/anime.js`.

**Names and trademarks.** The names and marks 「星玖工作室」, 「Ntarstudio」, 「玄玖灵犀」, 「Xael」, 「NT-Xhex」, 「空谷」, 「Ondra」, 「Wacmin」, 「TapMC」, 「Desop」, 「行简」 and 「Serica」 belong to Ntarstudio. MIT and Apache-2.0 grant copyright permissions only, not trademark rights.

Copyright (c) 2024–2026 Ntarstudio

---

## 20. NOTICE and Open-Source Compliance

Every third-party component and asset used by this project is disclosed item by item in [NOTICE](NOTICE).

| Component | How included | License | Modification |
|---|---|---|---|
| asorn/asorn-open | Source derivation | Apache-2.0 | Modified (interface and structure redesigned) |
| anime.js v2.0.2 | Whole file embedded | MIT | Unmodified |
| Typed.js 2.0.16 | unpkg CDN | MIT | Unmodified |

**Apache-2.0 clause 4 obligations are met**: the original copyright notice, the full licence text and a change statement are all retained.

**Process for adding a third-party component**: confirm licence compatibility with this project's MIT / Apache-2.0 → register it in `NOTICE` (name, version, copyright holder, licence, address, purpose, whether modified) → then commit. Where a licence cannot be confirmed, mark it "unconfirmed" and hold the merge.

---

Ntarstudio · <https://www.ntars.cn/>