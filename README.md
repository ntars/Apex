[简体中文](README.md) | [English](README_EN.md) | [日本語](README_JA.md) | [한국어](README_KO.md) | [Français](README_FR.md) | [Русский](README_RU.md) | [Español](README_ES.md) | [العربية](README_AR.md)

# Apex

**星玖工作室（Ntarstudio）的官网，以及十五个项目的总索引。**

The official site of Ntarstudio — and the index to thirteen projects.

> **本仓库的双重身份**：它既是工作室官网的源码（一个 HTML、一份样式表、几个原生脚本），也是**十五个项目的总索引**。本文的重点是后者：介绍每个项目是什么、做到哪一步、去哪里看。网站自身的实现细节压缩在第五章，不占主要篇幅。

![Status](https://img.shields.io/badge/status-online-2ea44f?style=flat-square)
[![GitHub license](https://img.shields.io/github/license/ntars/Apex?style=flat-square)](./LICENSE)
[![GitHub Star](https://img.shields.io/github/stars/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/stargazers)
[![GitHub Fork](https://img.shields.io/github/forks/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/network/members)
![GitHub Repo size](https://img.shields.io/github/repo-size/ntars/Apex?style=flat-square&color=3cb371)

[![Live](https://img.shields.io/badge/live-www.ntars.cn-0078d4.svg?style=flat-square)](https://www.ntars.cn/)
[![Projects](https://img.shields.io/badge/projects-13-8957e5.svg?style=flat-square)](#)
[![Build](https://img.shields.io/badge/build-none-2ea44f.svg?style=flat-square)](#)

---

## 一、项目名称与定位

> **仓库描述 / Description**：`星玖工作室官网与十五个开源项目总索引：一个 HTML、一份样式表、几个原生脚本 | The Ntarstudio official site and an index of fifteen open-source projects, in one HTML file and a stylesheet.`
>
> **话题标签 / Topics**（20 个，仅英文）：`static-site`, `vanilla-css`, `vanilla-javascript`, `no-framework`, `no-dependencies`, `single-page`, `landing-page`, `portfolio-site`, `studio-website`, `personal-website`, `pwa`, `service-worker`, `responsive-design`, `dark-mode`, `chinese-website`, `ntarstudio`, `frontend`, `html`, `css`, `javascript`


**名称**：Apex，意为顶点。作为工作室的官网，它承担的是「入口」而非「产品」的角色。

**一句话定位**：一个零依赖、零构建的单页静态站，用最少的代码把「这是谁、在做什么、去哪里看」三件事说清楚。

**定位的三条边界**：

1. **它是门牌，不是展厅**。不承载产品功能、不做在线演示、不内嵌文档站。访客要往下走，链接直达对应项目。
2. **它是静态文件，不是应用**。没有后端、没有数据库、没有账号体系。所有内容硬编码在 `index.html`，改一行文字就是一次提交。
3. **它是索引，不是内容源**。项目的真实信息在各项目自己的仓库与站点，本页只做汇总与跳转，不重复建设。

**为什么这个仓库的 README 要重点介绍项目**：官网首页的「星玖工作室出品」区块列出了全部十五个项目。这个列表与本文第三章、与 GitHub 自述文件三处同源。**任何想快速了解工作室在做什么的人，看这一页就够了**，不必逐个仓库翻。

---

## 二、项目简介

### 2.1 背景

工作室官网最常见的两种失败方式：一是做成 CMS 驱动的多页站，结果半年不更新，内容比产品还旧；二是做成炫技式的作品集，动画堆满首屏，访客找不到项目入口。

### 2.2 要解决的问题

访客打开首页，应当立即获得三个答案：**这是谁、他们在做什么、去哪里看**。超过三秒还没答出来，页面就是失败的。

### 2.3 核心思路

站点的全部职责只有三项：

| 职责 | 做法 |
|---|---|
| 建立品牌识别 | 首屏把「星玖工作室 / Ntarstudio / Ntars」三个称呼对应起来 |
| 导向开源项目 | 十五张卡片直连正式地址 |
| 信息如实 | 未上线、已下线的信息一律不出现在页面、关键词、结构化数据里 |

### 2.4 适用场景

- 小型独立工作室的官方门牌页；
- 需要长期稳定、几乎零维护的静态站；
- 作为「零构建前端」的教学样本（一个 HTML 如何组织好一个站点）。

### 2.5 非目标

本站不做的事同样明确：

- 没有账号、没有表单、没有 Cookie、没有统计埋点、没有广告、没有后端接口；
- 不使用 jQuery / Vue / React / UI 组件库，不使用 Tailwind，不使用 Vite / Webpack / Rollup；
- 不写 localStorage（唯一例外见 5.1 节的主题说明：刻意不写）。

---

## 三、核心功能

首页「星玖工作室出品」区块展示十五个项目，按状态分三组：已上线或已交付在前，开发中居中，排期开发在后；组内按项目名的拉丁字母升序排列。

**十五个项目 = Apex、Gitrule-skill、Ondra、Wacmin、Webroit、Xael、Amphoreus、Chiubay、Flutter-IDE、NovaKit、Relax、Serica、TapMC、Desop、Taycho-OS。** GitHub 是承载这些项目的平台，不算项目；Wacmin 内部的四个方向是它的实现细节，不单独列。

### 3.1 已发布、已交付与开发中

#### Apex · 已上线

| | |
|---|---|
| 是什么 | 你正在看的这个站点，工作室门牌与项目总索引 |
| 技术 | HTML · CSS · Vanilla JS |
| 许可 | MIT（`assets/css/base*.css` 含 Apache-2.0 派生规则，见 [LICENSING.md](LICENSING.md)） |
| 入口 | <https://www.ntars.cn/> |
| 仓库 | <https://github.com/ntars/Apex> |

一个 HTML、一份样式表、几个原生脚本。没有框架、没有构建、没有后端。零依赖意味着三年后还能跑。

**为什么值得看**：它是「零构建前端」的一个样本——一个 HTML 文件如何组织好一个站点，且六年不更新也不会失效。

#### Gitrule-skill · 已交付

| | |
|---|---|
| 是什么 | 一套覆盖项目全生命周期的通用规范模板：立项、需求、架构、开发、测试、部署、运维、迭代，以及文档、合规与 AI 程序化接入 |
| 技术 | Markdown（零第三方依赖）· Python CLI · MCP 服务器 |
| 规模 | 68 篇规范 × 12 种语言，同一标识在各语言目录一一对应 |
| 状态 | 已交付：CLI 校验 0 问题，Skill、专家包、MCP 服务器三种接入齐备 |
| 许可 | MIT |
| 仓库 | <https://github.com/ntars/Gitrule-skill> |

一份规范一个文件，各自独立、按需取用。配套零依赖 CLI 检查断链、孤岛、职责句、代码围栏、索引计数与占位符登记，`optimize` 只做可安全自动修复的项。

**为什么值得看**：它把「README 写哪 20 章、仓库怎么命名、简介与话题怎么设」这类口头约定变成可校验的文件与命令。本次十五个仓库的文档对齐即以它为唯一基准。

#### 空谷 Ondra · 产品内测中

| | |
|---|---|
| 是什么 | 全插件式桌面 AI 陪伴体：界面只读插件投影，情绪、记忆、上下文是三个核心机制，数据全留本机 |
| 技术 | Flutter（桌面与 Web）· Cordis 4.1.0（插件框架）· dsh 内核（Node） |
| 版本 | 内测 `2.0.0-alpha` |
| 平台 | macOS 可运行、Web 可构建；其余端只生成过工程 |
| 许可 | Apache-2.0 / MIT |
| 入口 | <https://ai.ntars.cn/> |
| 仓库 | <https://github.com/ntars/Ondra> |

三个核心机制：情绪（带惯性的状态量）、记忆（11 环链路）、上下文（冻结前缀 + 增量注入 + 预算装箱）。插件页把随包 18 条与装配层 75 条合并成 93 条，可逐条开关。

**为什么值得看**：它把「陪伴」拆成可分别工程化的机制，并用一个启动时序补丁把并发 apply 造成的 18 个插件静默降级从 55 条修到 0 条；界面与插件之间只有投影一层，页面不持有插件内部状态。

#### Wacmin · 可用

| | |
|---|---|
| 是什么 | macOS 与 Windows 的双向互通套件，并对外开放 AI 接入 |
| 技术 | Node.js · Python · Rust |
| 状态 | 四个方向全部完成，测试全部通过 |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/Wacmin> |

按「宿主 × 动作」填满四个方向，四个都已写完并通过测试：

| 顺位 | 方向 | 宿主动作 | 测试 |
|---|---|---|---|
| 1 | **Mac2Win** | 在 Mac 上产出 Windows 安装包 | 125 项 |
| 2 | **ExeOnMac** | 在 Mac 上运行 Windows 程序 | 319 项 |
| 3 | **Win2Mac** | 在 Windows 上产出 macOS 应用包 | 121 项 |
| 4 | **AppOnWin** | 在 Windows 上运行 macOS 程序 | 91 项 |

**再加一层 `ai/` 接入**：同一个调度层对外开四种形态——MCP server（供 Claude Desktop / WorkBuddy / Cline 调用）、统一命令行、Skill、专家包。协议层与传输层不到 900 行、零第三方依赖，没引入官方 SDK。

**为什么值得看**：它按确定性排序开发，把最可能失败的一环留到最后，并预先定义了降级路径——即使最后一环不成立，前三项仍成立。而事实证明这一环也成立了。另外那层 `ai/` 不是「顺手加个 MCP」，是把调度逻辑从 shell 壳里抽成 `directions.mjs` 后自然长出来的——抽出的过程还暴露了一个沉睡缺陷：`/api/status` 每次请求都会把 21 行中文用法写进 stdout 并把 `exitCode` 设成 2，console 从不读自己的 stdout 所以一直没被发现，但 MCP 规范要求 stdout 只出现协议消息，同一写法在 MCP 上是致命的。

#### Webroit · 已上线

| | |
|---|---|
| 是什么 | 浏览器里的安卓玩机工具箱，WebUSB 直连 ADB 与 Fastboot，57 项功能已实现、152 项规划 |
| 技术 | TypeScript · Vite · WebUSB · ya-webadb |
| 形态 | 纯静态站点，零后端、零安装、零驱动 |
| 许可 | Apache-2.0 / MIT |
| 入口 | <https://adb.ntars.cn/> |
| 仓库 | <https://github.com/ntars/Webroit> |

把 Android 玩机所需的一切搬进浏览器。底层用 Tango 实现 ADB 协议，交付的是玩机者能直接用的界面与流程——应用管理、文件浏览、终端、投屏、日志、刷机，57 项已实现、152 项规划，按风险分级。

**为什么值得看**：它把「环境准备」整层删掉了。传统路径是下载 Platform-Tools → 配 PATH → 装 USB 驱动 → 写 udev 规则 → 连设备 → 敲命令；它把前面五步压成「打开网页 → 点连接 → 点功能」。而真正的难点从来不是敲命令，是「装完了还是连不上」时那种分不清是线、是口、是驱动、还是 `adb.exe` 还挂在后台的时刻。

**另外两点值得记**：全部产物是静态 `dist/`，`grep -r "http" dist/` 里不含任何自有后端地址——数据不出本机不是承诺，是可验证的事实。以及它对风险做了分级，抄来的命令会改什么、能不能改回来，界面上都写着。

#### 玄玖灵犀 Xael · 产品已上线

| | |
|---|---|
| 是什么 | 本地离线的中华文化术数文献库，22 项功能从零演算，不查表、不联网 |
| 技术 | JavaScript（零依赖）· PWA · 微信小程序 · uni-app |
| 版本 | 5.0.0 |
| 许可 | Apache-2.0 / MIT |
| 入口 | <https://x.ntars.cn/> |
| 仓库 | <https://github.com/ntars/Xael> |

覆盖四柱八字、紫微斗数、奇门遁甲、大六壬、六爻、梅花易数、玄空飞星与黄历择吉。历法底座用天文级数实时求朔，不依赖历表；20 部公版古籍作为底本，逐条校正并标注证据强度。微信小程序与公众号同名可搜到。

**为什么值得看**：它把「不查表、能算就算」这条原则贯彻到了底，且对每条结论都标注了文献依据与不确定处。

#### Amphoreus · 开发中

| | |
|---|---|
| 是什么 | 只看不操控的翁法罗斯世界模拟器：十二位泰坦、十三位黄金裔、十二枚火种由代码演算，附纯 CSS 复刻的「如我所书」书册 |
| 技术 | Python 3.11+（仅标准库）· SQLite · HTML / CSS / Vanilla JS |
| 状态 | 开发中：模拟器可运行、`/book` 书册可用；官方基准截图未齐，不宣称逐像素一致 |
| 平台 | macOS / Linux / Windows（依赖仅 Python 标准库） |
| 许可 | MIT |
| 仓库 | <https://github.com/ntars/Amphoreus> |

同一种子必得同一段历史，换种子即换一个翁法罗斯；规则引擎决定「发生了什么」，本地模型只决定「怎么讲」。网页端运行时不加载任何位图或 SVG，图案全部由渐变、边框与 `clip-path` 绘制。

**为什么值得看**：它把「确定性叙事」与「零图片界面」同时做成了可复核的工程约束，而不是概念演示。

#### Chiubay 玖白 · 研究原型

| | |
|---|---|
| 是什么 | 从零养育一个会自己长大的智能体：长期个人 AGI 机制研究，六个发育环逐步叠加 |
| 技术 | Python · NumPy（自研张量、手写反传，禁用 torch / JAX / 预训练权重） |
| 状态 | 研究原型：自研张量栈与 E3 认同环实验可运行，其余五环仍在纸面 |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/Chiubay> |

目标不是交付「人级 AGI」，而是把「一个智能体如何被养育成形」拆成可证伪的机制实验。每个结论只写验证了什么，不写达成了什么。

**为什么值得看**：它把训练规则、评估协议与失败边界全部公开，并明确承认算力差距是物理边界而非优化问题。

#### Flutter-IDE · 可用 `0.2.0`

| | |
|---|---|
| 是什么 | 源码优先的 Flutter 可视化搭建 IDE：画布拖拽、属性面板改值，产出可脱离工具维护的 Dart 代码 |
| 技术 | Dart 3.14+ · Flutter Desktop |
| 版本 | `0.2.0` |
| 状态 | 可用：CLI 校验/生成、桌面端文件树与多标签编辑、画布拖拽、属性编辑、VM 点选与热重载、macOS DMG/ZIP 可分发 |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/Flutter-IDE> |

判定项目是否成立的唯一标准：删掉 IDE，项目还能否正常 `flutter run`。因此意图大纲、覆盖层与设计令牌全部是进 git 的明文文件，不存在只活在工具里的项目结构。

**为什么值得看**：它把「不被工具锁定」写成三条可验收的标准——无私有 Schema、改一处只有一处 diff、同一输入两次生成结果一致，而不是一句口号。

#### NovaKit · 骨架阶段

| | |
|---|---|
| 是什么 | 装完系统只装这一套的离线桌面工具箱：文件、图片、文本与系统小工具，不联网、不要账号 |
| 技术 | Rust（edition 2024）· Tauri 2 |
| 状态 | 骨架阶段：工程与 36 个工具的清单已定，业务代码在搭建，无发行版 |
| 平台 | 首发 macOS，Windows / Linux 计划中 |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/NovaKit> |

工具按四层组织——纯 Rust、系统能力、外部组件、进程插件——每层对应不同的实现与验收方式。插件走 JSON-RPC 2.0 over stdio，权限默认全拒。

**为什么值得看**：它用「装完系统第一周会用到什么」反推工具清单，并用分层把安全边界写死，而不是堆成全能软件。

#### 悠然 Relax · 早期开发

| | |
|---|---|
| 是什么 | 家庭自托管的通讯、日程、文件与相册平台：单机单进程服务端，Android 客户端访问，数据不出家门 |
| 技术 | Rust · Tauri 2 · axum · SQLite · React + TypeScript |
| 状态 | 早期开发：服务端鉴权、同步、聊天、公告、日程、文件等路由骨架已落地，业务闭环未完成 |
| 平台 | 服务端 macOS / Linux，客户端 Android API 24+ |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/Relax> |

业务逻辑全在 Rust：前端只渲染、只 `invoke()`，不发起网络请求、不直连 SQLite、不持久化 token。消息进 outbox，恢复后按 `opId` 幂等提交。

**为什么值得看**：它把「数据自主」落成五道可机检的架构锁，而不是一句隐私口号。

#### 行简 Serica · 骨架阶段

| | |
|---|---|
| 是什么 | 面向多端同步应用的编程语言：全中文表达，源码扩展名 `.serica`，命令行入口 `serica`，产物是原生可执行文件 |
| 技术 | Go（种子编译器 stage0）· 自举路线 · 直接写出 Mach-O |
| 版本 | 阶段 `P1b` pre-alpha；P0b 已于 2026-11-20 在 macOS arm64 通过硬验收 |
| 规模 | 种子 1928 行，上限 5000 行，逐行归因，自举后整目录删除 |
| 许可 | Apache-2.0（核心层与种子层）/ MIT（规范层与生态层） |
| 平台 | 已验证 macOS arm64，其余平台未验 |
| 仓库 | <https://github.com/ntars/Serica> |

种子编译器不生成 C，不调用 LLVM、汇编器或链接器，直接写出 Mach-O；中文标点在词法层是语法而不是排版，诊断同时给出码位列与显示列（`第 3 行第 38 列（显示第 55 格）`）；同一份源码重复构建字节一致。当前能用的只有编译期常量、码位切片、整数四则、位运算、编译期常量数组与一个声明式窗口，**不能用来写生产软件**。

**为什么值得看**：它把「中文不只是关键字翻译」落成可复核的工程约束——5000 行种子上限、逐行归因表、自举后删除种子，以及一条 `file` 就能验的产物类型，而不是一份愿景文档。

#### TapMC · 骨架阶段

| | |
|---|---|
| 是什么 | 可模组化的多人沙盒游戏骨架：Flutter 七端前端 + Java 服务端，只通过一份 JSON-RPC 2.0 协议耦合 |
| 技术 | Flutter（前端）· Java 21（后端） |
| 状态 | 骨架阶段：链路已通，后端 61 个测试、前端 18 个测试通过；无发行版 |
| 平台 | Web 与 Android 构建通过，其余五端待验 |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/TapMC> |

后端是唯一真相来源，前端只负责呈现与输入；世界为 24×16 二维网格、五种方块；模组只能拿到 `ModContext`、拿不到 `WorldGrid`，绕不过规则。

**为什么值得看**：它把「规则在哪算」用编译期约束钉死，而不是靠评审纪律；内核零网络依赖，整局逻辑可不起端口跑单测（22 个用例）。

### 3.2 排期开发 / Planned

**Desop 只有资料，没有可运行代码。** 状态口径严格区分「已发布」「开发初期」与「排期」，不把规划说成已实现。

#### Desop · 可构建 MVP `0.2.0`

| | |
|---|---|
| 是什么 | Windows 端桌面美化套装：dock 栏、顶部栏、桌面小组件、灵动岛 |
| 技术 | Python 3.11+ · PySide6（用户态） |
| 版本 | `0.2.0` |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/Desop> |

零系统改动，纯用户态运行，卸载即还原。四个组件共享一套设计令牌，可单独启用。性能预算作为发布门槛：空闲 CPU < 1%、内存 < 150 MB、dock 放大 ≥ 55 fps，达不到不发布。

**为什么值得看**：它对「美化工具会拖慢系统」这个普遍痛点给了硬指标，而不是说「后续优化」。

#### Taycho-OS 太初 · 设计阶段（占位）

| | |
|---|---|
| 是什么 | 以行简（Serica）从零写出的原生系统：运行模型、能力边界、消息机制、窗口与文本全部重写 |
| 技术 | Serica（规划）· 原生可执行文件 |
| 状态 | 设计阶段：仅有设计文档与占位仓库，尚无代码 |
| 许可 | Apache-2.0 / MIT |
| 仓库 | <https://github.com/ntars/Taycho-OS> |

不基于任何既有内核、运行时或图形栈；一切 IO 与系统访问必须显式声明能力，未声明即拒绝。

**为什么值得看**：它把「从零」写成可机器复核的边界条件，而不是一句宣言。

### 3.3 状态口径

**官网状态与产品状态不等价**——官网在跑不代表软件能装，软件在跑也不代表官网能开。

| 项目 | 状态 | 含义 |
|---|---|---|
| Apex | 已上线 | 站点在跑，源码公开 |
| Gitrule-skill | 已交付 | 68 篇规范 × 12 种语言，CLI 校验 0 问题；不设发行版号，按主干交付 |
| Ondra | 产品内测中 | `2.0.0-alpha`：macOS 可运行、Web 可构建，其余端只生成过工程 |
| Wacmin | 可用 | 四个方向全部完成并通过测试，含 CLI 与 MCP 接入；不是「内测」也不是「正式版」，它本就以 CLI 形态交付 |
| Webroit | 已上线 | 静态站点在 `adb.ntars.cn` 运行，57 项功能可用，源码公开 |
| Xael | 产品已上线 | 有正式版本（`5.0.0`），可下载可用 |
| Amphoreus | 开发中 | 模拟器与书册可本地运行，官方基准未齐，未宣称逐像素一致 |
| Flutter-IDE | 可用 | `0.2.0`：桌面端编辑、画布拖拽、属性面板与 macOS 分发包可用 |
| NovaKit | 骨架阶段 | Tauri 2 工程与 36 个工具清单就位，业务代码未开始 |
| Chiubay | 研究原型 | 自研张量栈与 E3 认同环实验可运行，其余五环仍在纸面 |
| Taycho-OS | 设计阶段 | 仅有设计文档与占位仓库，尚无代码 |
| 悠然 Relax | 早期开发 | 服务端路由骨架已落地，业务闭环未完成，无 APK |
| 行简 Serica | 骨架阶段 | 种子编译器能编译 P0b/P1b 子集并直出 Mach-O，P0b 已在 macOS arm64 通过验收；无发行版，不能写生产软件 |
| TapMC | 骨架阶段 | 链路已通、79 个测试通过，但没有发行版 |
| Desop | 排期开发 | 只有文档，没有可运行代码 |

**为什么排期项目也进官网卡片**：官网是工作室的门牌，展示的是「在做什么」，不只是「已经做成了什么」。排期项目标注清楚状态即可，访客看到「排期开发」四个字就知道点进去没有可下载内容——这比藏着不展示更诚实。

---

## 四、核心特性

### 亮点一：十五个项目集中呈现，三处口径同源

- **亮点名称**：单页总索引。
- **价值**：解决「想知道这个工作室在做什么，得逐个仓库翻」的问题。
- **实现方式**：首页卡片、本文第三章、GitHub 自述文件三处列出同一份清单，状态口径一致。
- **差异化**：多数个人主页只列已发布项目，或者散落在多个仓库的 README 里。
- **证据**：三处的项目名称、状态、链接逐条对应，见 5.9 节的状态表。

### 亮点二：零依赖零构建，改完刷新即生效

- **亮点名称**：无工具链。
- **价值**：解决「半年不更新就再也跑不起来」的问题。依赖越多，一年后 `npm install` 失败的概率越高。
- **实现方式**：仓库里没有 `node_modules`、没有 `package.json`、没有锁文件。`python3 -m http.server 8000` 即可本地预览。
- **差异化**：多数「极简站点」仍在用 Vite 或 Webpack，理由是「反正模板有」。
- **证据**：仓库根目录无 `package.json`；部署路径为「推 main → EdgeOne Pages 自动发布」。

### 亮点三：主题跟随系统，首帧不闪白

- **亮点名称**：两帧锁定的首帧主题。
- **价值**：解决暗色系统下打开页面时的一下白闪。
- **实现方式**：`<head>` 里同步执行的内联脚本读 `prefers-color-scheme`，结果写入 `<html data-theme>`；脚本先加 `theme-lock` 抑制过渡，主题落定后连续两帧 `requestAnimationFrame` 才移除。
- **差异化**：常见做法是等 `DOMContentLoaded` 再设主题，或干脆不做防闪。
- **证据**：`html:not(.theme-lock)` 下的统一 0.5s 过渡规则。

### 亮点四：卡片光晕跟着指针走，不动 DOM

- **亮点名称**：CSS 变量驱动的指针光晕。
- **价值**：解决「悬停效果引发布局重排」的问题。
- **实现方式**：`app.min.js` 算出指针相对卡片的坐标写进 `--mouse-x` / `--mouse-y`；卡片 `::before` 用 `radial-gradient` 画出跟随的光晕。
- **差异化**：常见的跟随光晕用 JS 移动绝对定位元素，每次 `mousemove` 都触发合成层重排。
- **证据**：`app.min.js` 全文只做坐标计算与变量写入。

### 亮点五：弹窗滚动的两个易错点都被处理

- **亮点名称**：滚动条补偿与退场方向。
- **价值**：解决两个几乎所有自建弹窗都会犯的错——打开时页面右移，关闭时面板被「吸」向一角。
- **实现方式**：打开时补 `padding-right` 再设 `overflow: hidden`；关闭时等 `opacity` 过渡结束（含 500ms 兜底定时器）再恢复滚动，退场仅过渡 `opacity`，不碰 `transform`。
- **差异化**：改 `transform` 会让面板朝变换原点移动，观感上像被吸附。
- **证据**：`prefers-reduced-motion` 下动画被跳过，500ms 定时器是唯一保证弹窗能关掉的路径。

---

## 五、设计细节与工程取舍

**本章是本文中唯一讲网站自身实现的部分。** 篇幅有意压缩——项目介绍才是重点。

### 5.1 主题：跟随系统，手动可覆盖，刷新不记住

双击「星玖工作室出品」可手动翻转，并同步 `<meta name="theme-color">`，让移动端地址栏同色。

**手动状态不写 localStorage——这是故意的。** 官网的默认体验是跟随系统，多存一个开关就多一处需要解释的状态。刷新即回到系统偏好。

### 5.2 页面五块

页面自上而下五块：问候区、分割线、项目区、右上角联系我们入口、页脚。外加四个常驻叠加层（烟花 canvas、拖尾 canvas、背景粒子 canvas、底部装饰）。

没有路由，没有虚拟 DOM，滚动由浏览器原生完成。

### 5.3 问候区的三档设备

| 设备 | 判定 | 显示 |
|---|---|---|
| 手机 | 视口 < 768px | Hi, I'm **Ntars** |
| 平板 | 768–1180px 且具备触摸 | 横屏工作室模式，竖屏个人模式 |
| 桌面 | 其余 | Hi, We're **Ntarstudio** |

平板判定额外要求 `ontouchstart in window` 或 `navigator.maxTouchPoints > 0`，否则大窗口桌面浏览器会被误判。

### 5.4 项目卡片：配置驱动

卡片由 `PROJECTS` 数组渲染，十五个条目各含标题、描述、链接、可选图标四个字段。`grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))`，间距 16px，桌面三列、窄屏一列，不需要写媒体查询。

改项目状态是改一行数据，不是改一段 HTML——避免「改了卡片忘了改元信息」和「卡片结构漂移」两类历史问题。

### 5.5 脚本分六个文件而不是一个

| 文件 | 职责 |
|---|---|
| `security.js` | 禁用选中/复制/右键/快捷键，篡改监测 |
| `app.min.js` | 卡片光晕：指针坐标 → CSS 变量 |
| `anime.js` | anime.js v2.0.2（第三方，MIT，不修改） |
| `firework.js` | 烟花粒子 |
| `trail.js` | 指针拖尾 |
| `bg.js` | 背景粒子与连线 |

每个文件只负责一件事，出现问题时可以单独移除。唯一的硬依赖是 `firework.js` 依赖 `anime.js`，因此加载顺序固定为 `security → app.min → anime → firework → trail → bg`。

### 5.6 缓存版本号是最容易忘的一步

**`CACHE_NAME` 当前为 `ntarstudio-v10`。** 只要动了预缓存清单里的任何资源（包括通过 CDN 引入的 Typed.js），就必须升版本号，否则回访用户会长期停在旧缓存上。

### 5.7 安全防护的诚实边界

`security.js` 拦截选中、复制、剪切、右键、拖拽、F12 与查看源码类快捷键。

**需要说清楚的是：这些措施只提高随手复制的门槛，不构成任何内容保护。** 前端代码对访问者始终可见，任何脚本都改变不了这一点。

### 5.8 CSP 白名单

| 指令 | 取值 |
|---|---|
| `default-src` / `script-src` | `'self'`、内联、`https://unpkg.com` |
| `img-src` | `'self'` 与 `data:` |
| `frame-src` / `object-src` | `'none'` |
| `connect-src` | `'self'`（页面不发起外部接口请求） |

另带 `nosniff`、`X-Frame-Options: DENY`、`referrer: no-referrer`。

### 5.9 三处口径同改的纪律

项目状态变化（上线、下线、换域名）时，以下三处必须同时更新：

1. `index.html` 的 `PROJECTS` 数组；
2. 本文第三章「十五个项目」；
3. GitHub 自述文件 `ntars/ntars` 的项目表。

**已下线项目不得以任何形式回流**——不出现在页面、关键词或结构化数据里。

---

## 六、技术栈与依赖清单

### 6.1 技术栈

| 层 | 选型 |
|---|---|
| 结构 | 原生 HTML5，语义标签 + `role` 补充 |
| 样式 | 原生 CSS：自定义属性 + Grid + Flexbox |
| 交互 | 原生 JavaScript（以 ES5 语法为主） |
| 动画 | anime.js v2.0.2，仅烟花粒子使用 |
| 字体 | 系统字体栈，不加载网络字体 |
| 离线 | Service Worker + Web App Manifest |
| 部署 | EdgeOne Pages |

### 6.2 第三方组件

| 组件 | 版本 | 版权人 | 许可 | 引入方式 | 用途 |
|---|---|---|---|---|---|
| asorn/asorn-open | — | asorn | Apache-2.0 | 源码派生 | 初始底座 |
| anime.js | v2.0.2 | Julian Garnier (2017) | MIT | 整文件内嵌 | 烟花时间轴与缓动 |
| Typed.js | 2.0.16 | Matt Boldt | MIT | unpkg CDN + SW 预缓存 | 问候语打字 |

**派生关系**：本项目在 asorn/asorn-open 基础上修改、扩展并重新设计了界面与结构，属衍生作品。依 Apache-2.0 第 4 条已保留原版权声明、许可全文与变更说明。

### 6.3 明确未使用

第三方网络字体 · 第三方图标库 · 前端框架与 UI 库 · 统计与埋点 · 广告与评论客服组件 · Cookie 与本地存储写入 · 后端接口与数据库。

### 6.4 间接依赖

无。不存在传递依赖。

---

## 七、安装与部署

```bash
python3 -m http.server 8000
# 打开 http://localhost:8000
```

没有构建步骤，改完刷新即生效。Service Worker 只在 `localhost` 或 HTTPS 下注册，`file://` 不支持。

**部署只有一条路**：推 `main` → EdgeOne Pages 自动发布，主域名 `www.ntars.cn` 指向该站。仓库不含任何 workflow 文件。

---

## 八、快速开始

### 8.1 看项目

直接读本文第三章「十五个项目」，或访问首页 <https://www.ntars.cn/>。

### 8.2 本地跑网站

1. `git clone https://github.com/ntars/Apex.git`
2. `cd Apex && python3 -m http.server 8000`
3. 浏览器打开 `http://localhost:8000`
4. 双击「星玖工作室出品」验证主题切换
5. 拖窄窗口到 768px 以下验证手机模式文案
6. 点击右上角「联系我们」验证弹窗

---

## 九、配置说明

本站无配置文件。所有可调内容集中在三处：

| 内容 | 位置 | 改什么 |
|---|---|---|
| 项目卡片 | `index.html` 的 `PROJECTS` 数组 | 标题、描述、链接、可选图标 |
| 主题色 | `assets/css/base.css` 的 `:root` 与 `[data-theme="dark"]` | CSS 自定义属性 |
| 缓存版本 | `sw.js` 的 `CACHE_NAME` | 动了预缓存资源就必须升版 |

---

## 十、API 与模块说明

本站无 API。脚本模块职责见 5.5 节。加载顺序固定：`security → app.min → anime → firework → trail → bg`。

---

## 十一、目录结构

```
Apex/
├── index.html                 # 结构 + 元信息 + 四段内联脚本
├── manifest.json              # PWA 清单
├── sw.js                      # Service Worker
├── LICENSE                    # MIT 全文
├── LICENSE-Apache-2.0.txt     # Apache-2.0 全文（asorn 派生部分）
├── NOTICE                     # 版权与第三方声明
├── README.md / README_EN.md
└── assets/
    ├── css/
    │   ├── base.css           # 唯一被加载的样式表
    │   ├── base.scss          # 与 base.css 对应的样式源
    │   └── base.min.css       # 压缩产物
    ├── js/
    │   ├── security.js
    │   ├── app.min.js
    │   ├── anime.js           # 第三方，MIT
    │   ├── firework.js
    │   ├── trail.js
    │   └── bg.js
    └── img/                   # 自研 N+T 词标与 PWA 图标
```

---

## 十二、性能表现

| 指标 | 数值 | 说明 |
|---|---|---|
| 构建步骤 | 0 步 | 无打包、无压缩流程 |
| 首屏外链 | 1 个 | Typed.js（unpkg CDN，已预缓存） |
| 网络字体 | 0 | 系统字体栈 |
| 布局重排 | 0 | 光晕仅改 CSS 变量 |
| 二次访问 | 走缓存 | Service Worker 缓存优先 |

---

## 十三、安全与隐私

| 维度 | 做法 |
|---|---|
| Cookie | 不使用 |
| 本地存储 | 不写入（主题手动状态刻意不持久化） |
| 统计埋点 | 无 |
| 第三方请求 | 仅 Typed.js（unpkg CDN） |
| CSP | 声明白名单，`object-src` / `frame-src` 为 `'none'` |
| 点击劫持 | `X-Frame-Options: DENY` |
| 引用泄漏 | `referrer: no-referrer` |

**前端内容保护的诚实说明**：`security.js` 只提高随手复制的门槛，不构成任何内容保护。

---

## 十四、兼容性说明

| 环境 | 状态 | 说明 |
|---|---|---|
| 现代浏览器 | ✅ 完整 | 原生 CSS 自定义属性 + Grid |
| 旧版浏览器 | ⚠️ 降级 | 脚本以 ES5 语法为主；主题不生效但内容可读 |
| 手机（< 768px） | ✅ | 满宽单列 |
| 平板（768–1180px 触摸） | ✅ | 横竖屏双模式 |
| 桌面（≥ 1180px） | ✅ | 三列卡片 |
| `file://` 直接打开 | ⚠️ 部分 | Service Worker 不注册，其余正常 |

---

## 十五、已知问题与限制

1. **缓存版本号依赖人工**：`CACHE_NAME` 忘记升版会导致回访用户长期停在旧缓存，且不会有任何报错。
2. **主题手动状态不持久化**：刷新后回到系统偏好，这是刻意设计而非缺陷。
3. **平板端禁用点击切换主题**：模式由方向决定，手动状态会与方向判定冲突。
4. **前端内容保护无效**：`security.js` 只提高门槛。
5. **Typed.js 走 CDN**：unpkg 不可达时打字效果失效，但不影响其余内容。
6. **排期项目的卡片无可下载内容**：这是状态如实标注的代价，换来的是「不把规划说成已实现」。

---

## 十六、更新日志

更新日志统一写在 **GitHub 发行版**页面：<https://github.com/ntars/Apex/releases>

README 描述站点当前状态，发行版记录每次改了什么，两者不混写。

---

## 十七、后续路线图

1. **缓存版本自动化**：用构建时的资源哈希替代手写 `CACHE_NAME`。
2. **卡片图标**：十五个项目的图标备好后挂载，当前均为 `icon: null`。
3. **无障碍审计**：已有 `role`、`tabindex`、`aria-*`，但未做完整的键盘走查与读屏测试。
4. **减少第三方依赖**：Typed.js 功能简单，可用约 40 行原生代码替代。
5. **OG 预览图**：当前无 `og:image`，社交平台分享时无缩略图。

---

## 十八、参与贡献

### 18.1 改动前自查

1. 十五张卡片的标题、描述、链接与项目真实状态一致；
2. `description`、`keywords`、`og:*`、JSON-LD、`canonical` 与正文口径同步；
3. 动了预缓存里的资源，`sw.js` 的 `CACHE_NAME` 已升版；
4. 亮色与暗色两套主题都看过；
5. 手机、平板、桌面三档宽度下无截断与溢出；
6. 弹窗打开时背景不滚、关闭后滚动位置不跳；
7. **项目状态变化时三处同改**（`PROJECTS` 数组、本文第三章、GitHub 自述文件）。

### 18.2 发布纪律

- 内容变更后必须检查 `CACHE_NAME`；
- 项目状态变化时，卡片、元信息、本文档状态表三处同改；
- 已下线项目不得以任何形式回到页面、关键词或结构化数据；
- 新增第三方组件前先确认许可兼容，并在 `NOTICE` 登记后才提交。

### 18.3 联系方式

| 渠道 | 地址 |
|---|---|
| 官网 | <https://www.ntars.cn/> |
| GitHub | <https://github.com/ntars> |
| 自述文件 | <https://github.com/ntars/ntars> |
| 邮箱 | <ntars@qq.com> · <ntarsx@163.com> |

---

## 十九、版权与许可

| 范围 | 许可 |
|---|---|
| 自研代码（结构、样式、脚本及后续改动） | MIT，见 [`LICENSE`](LICENSE) |
| `assets/css/base.css` 与 `base.min.css` 中派生自 asorn/asorn-open 的规则 | Apache-2.0，见 [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| 品牌名称、Logo、界面设计 | 保留所有权利，见 [`NOTICE`](NOTICE) |

**默认归属**：上表未列出的本项目自研文件，一律适用根 `LICENSE`（MIT）。

**这两个文件是「单文件内混合」**：派生规则受 Apache-2.0，其余规则受 MIT。拿到文件的人不必把整份文件当 Apache-2.0 处理，但也不能因为整仓是 MIT 就把 `LICENSE-Apache-2.0.txt` 删掉——第 4 条 a/b/d 项的义务随派生部分走，与仓库主许可无关。逐路径路由见 [LICENSING.md](LICENSING.md)。

再分发须一并保留：`NOTICE`、`LICENSE`、`LICENSE-Apache-2.0.txt`、`assets/js/anime.js` 文件头的版权与许可声明。

**名称与商标**。「星玖工作室」「Ntarstudio」「玄玖灵犀」「Xael」「NT-Xhex」「空谷」「Ondra」「Wacmin」「TapMC」「Desop」「行简」「Serica」等名称与标识归星玖工作室所有。MIT 与 Apache-2.0 只给代码权利，不给商标权。

Copyright (c) 2024–2026 星玖工作室 Ntarstudio

---

## 二十、NOTICE 开源合规声明

本项目使用的全部第三方软件、组件与素材，已在 [NOTICE](NOTICE) 文件中逐项披露。

| 组件 | 引入方式 | 许可 | 修改情况 |
|---|---|---|---|
| asorn/asorn-open | 源码派生 | Apache-2.0 | 已修改（界面与结构重新设计） |
| anime.js v2.0.2 | 整文件内嵌 | MIT | 未修改 |
| Typed.js 2.0.16 | unpkg CDN | MIT | 未修改 |

**Apache-2.0 第 4 条义务已履行**：保留原版权声明、许可全文与变更说明三件套。

**新增第三方组件的流程**：先确认许可与本项目 MIT / Apache-2.0 兼容 → 在 `NOTICE` 登记（名称、版本、版权人、许可、地址、用途、是否修改）→ 再提交代码。无法确认许可证归属的，标注「待确认」并暂不合入。

---

Ntarstudio（星玖工作室）· <https://www.ntars.cn/>
