**简体中文** | [English](README.en.md)

# 星玖工作室 Ntarstudio 官网主页

星玖工作室（Ntarstudio）官方品牌主页，同时作为在营项目的统一入口。站点为单页静态应用，不依赖前端框架、无构建流程、无后端服务，全部内容在浏览器本地渲染。

| 项 | 内容 |
|---|---|
| 项目全称 | 星玖工作室官网（Ntarstudio Official Site） |
| 项目代号 | NT-Studio |
| 线上地址 | https://www.ntars.cn/ |
| 源码仓库 | https://github.com/ntars/NT-Studio |
| 站点形态 | 单页静态站点（SPA-lite）· PWA 可安装 |
| 页面规模 | 1 个 HTML 文件 · 1 份主样式表 · 6 个页面脚本 · 1 个 Service Worker |
| 自研代码许可 | MIT |
| 派生部分许可 | Apache License 2.0 |
| 备案号 | 蜀ICP备2026027050号 |
| 版权 | Copyright (c) 2024–2026 星玖工作室 Ntarstudio |

---

## 一、项目说明

### 1.1 定位

本项目是星玖工作室的品牌门面与项目分发入口，解决三个问题：

1. **品牌识别**：在首屏建立「星玖工作室 / Ntarstudio / Ntars」三者之间的对应关系；
2. **项目导航**：将访客导向在营项目的正式地址，并如实标注各自的上线状态；
3. **信息准确**：任何已下线、未上线的内容均不出现在页面与元信息中，不产生死链，不产生误导。

站点不使用 CMS，不接入评论、统计、广告或任何第三方脚本（Typed.js 除外，见第四章）。所有文案与链接直接维护在 `index.html` 中，改动即生效。

### 1.2 职责边界

**本项目负责**：品牌展示、项目导航、联系方式聚合、PWA 安装能力、搜索引擎结构化描述。

**本项目不负责**：

- 不承载任何子项目的具体功能，子项目均为独立域名、独立仓库、独立许可；
- 不收集用户数据，无账号体系，无表单提交，无 Cookie 写入；
- 不提供内容管理后台，页面更新通过 Git 提交完成。

### 1.3 在营项目

| 项目 | 定位 | 形态 | 状态 | 正式地址 | 代码许可 |
|---|---|---|---|---|---|
| **玄玖灵犀 Xael**（NT-Xhex） | 中国传统术数文献整理、校勘与数字化演算工具 | 微信小程序（主）· 浏览器 PWA · uni-app 多端 · AI / 命令行调用 | 产品已上线（v4.3.0），官网筹备中 | [github.com/ntars/Xael](https://github.com/ntars/Xael)（官网 `x.ntars.cn` 上线后切换） | AGPL-3.0 |
| **元鸣 Ondra** | 桌面端 AI 拟人伴侣（装配人格、记忆、情绪、语音与形象；技术栈含 NT-Dpet 发行版与 NT-Sine 本地模型） | Electron 桌面端 · 本地部署（Apple Silicon / MLX） | 官网已上线（`ai.ntars.cn`），软件未发布 | [ai.ntars.cn](https://ai.ntars.cn/) | AGPL-3.0-or-later / AGPL-3.0 |

两个项目的状态标注遵循同一原则：**区分「官网状态」与「产品状态」**。

- 玄玖灵犀 Xael：产品本体（NT-Xhex v4.3.0，`version.json` 为唯一版本真值）已在各端上线；其官网 `x.ntars.cn` 截至 2026-10-27 尚无 DNS A 记录、未对外解析，因此卡片不挂官网链接、状态如实标注「产品已上线，官网筹备中」，官网地址上线后再切换。
- 元鸣 Ondra：官网 `ai.ntars.cn`（NT-Sine 站点）已解析并部署上线，可正常访问，卡片状态标注「官网已上线」；桌面端软件本体（NT-Dpet，当前 0.3.0 S0）尚未发布，不存在可安装产物，与官网状态分开表述，避免访客将官网存在误读为产品可用。

### 1.4 已下线的项目

以下项目已停止运营，域名已停止解析，页面正文与全部元信息中均已移除。此处保留记录，用于说明历史信息与当前口径的差异：

| 旧项目 | 原域名 | 当前状态 | 处理方式 |
|---|---|---|---|
| 玄玖知识库 NT-Know | `k.ntars.cn` | 已下线，无 DNS A 记录 | 卡片、meta、keywords、JSON-LD 全部移除 |
| 玄玖测试库 NT-List | `q.ntars.cn` | 已下线，无 DNS A 记录 | 卡片、meta、keywords、JSON-LD 全部移除 |

如在其他页面、搜索引擎快照或旧版截图中见到上述名称，均属过期信息，应以本页与两个在营项目的正式地址为准。

---

## 二、站点结构

### 2.1 页面组成

页面自上而下由五个区块构成，均为静态结构，无路由：

| 区块 | 内容 | 交互 |
|---|---|---|
| 问候区 | 「Hi, I'm Ntars」/「Hi, We're Ntarstudio」+ 循环打字文案 | 点击名字切换个人/工作室模式；双击「星玖工作室出品」切换主题 |
| 分割线 | 横向虚线，视觉上分隔品牌区与项目区 | 无 |
| 项目区 | 标题「星玖工作室出品」+ 两张项目卡片 | 悬停光晕跟随鼠标；点击新窗口打开 |
| 联系我们 | 右上角固定文字入口 + 模态弹窗 | 点击/回车打开，遮罩、关闭按钮、`Esc` 关闭 |
| 页脚 | 备案号 + 版权行 | 备案号链接至工信部备案系统 |

叠加层：全屏 `canvas` 烟花粒子、固定定位的底部装饰（光晕、上升星星、地球圆）、背景点阵。

### 2.2 目录结构

```
NT-Studio/
├── index.html                            # 页面结构、元信息、内联逻辑（主题初始化、设备判定、弹窗、PWA 注册）
├── manifest.json                         # PWA 清单：名称、图标、启动方式、主题色
├── sw.js                                 # Service Worker：预缓存、缓存优先、后台更新、旧缓存清理
├── README.md                             # 本项目文档
├── LICENSE                               # MIT 协议全文（自研代码）
├── LICENSE-Apache-2.0.txt                # Apache-2.0 协议全文（派生自 asorn/asorn-open 的部分）
├── NOTICE                                # 版权与第三方组件声明（法律文件）
├── 开源方案扫描.md                        # 三项目开源方案采纳盘点（可立即采用/需评估/暂不可用）
├── baidu_verify_codeva-C4tp7NQbk5.html   # 百度搜索资源平台站点验证文件
├── tencent-cloud-config.yml              # 腾讯云 COS 部署的补充配置（本项目当前不用）
└── assets/
    ├── css/
    │   ├── base.css                      # 唯一被页面加载的样式表
    │   ├── base.scss                     # 底座时期的历史样式源，未被引用
    │   └── base.min.css                  # 历史压缩产物，未被引用
    ├── js/
    │   ├── security.js                   # 安全防护：禁止选中、复制、右键、快捷键，篡改监测
    │   ├── app.min.js                    # 卡片光晕：鼠标坐标写入 CSS 变量
    │   ├── anime.js                      # anime.js v2.0.2（第三方，MIT）
    │   ├── firework.js                   # 烟花粒子：点击/触摸触发
    │   ├── trail.js                      # 鼠标拖尾：指针移动生成渐变粒子
    │   └── bg.js                         # 背景粒子：浮动节点与连线，随指针排斥
    └── img/
        ├── icon.svg                      # 主图标（SVG，favicon 首选）
        ├── favicon-color.svg             # 彩色站点图标
        ├── apple-touch-icon.png          # iOS 主屏图标 180×180
        ├── icon-192.png                  # PWA 图标 192×192
        └── icon-512.png                  # PWA 图标 512×512
```

关于 `base.scss` 与 `base.min.css`：两者派生自 asorn/asorn-open 底座时期，与当前样式已不同步（`base.scss` 仍包含 about、blog 等本站未使用的模块）。它们不参与构建、不被任何页面引用，保留原因是不擅自删除带有上游来源痕迹的文件。确认无需追溯后，可在独立提交中一并移除。

### 2.3 构建与运行方式

本项目无构建步骤，无包管理器依赖，无编译产物。`index.html` 即为最终产物，直接由静态服务器提供即可。样式修改直接编辑 `assets/css/base.css`。

---

## 三、功能与实现细节

### 3.1 主题系统

**判定顺序**（在 `<head>` 内联脚本中同步执行，先于样式表加载）：

1. 读取 `window.matchMedia('(prefers-color-scheme: dark)')`。若该媒体查询可用（`media !== 'not all'`），按系统偏好取值；
2. 若不可用，按本地时间兜底：6:00–18:00 为亮色，其余时段为暗色；
3. 将结果写入 `<html data-theme>`，同时设置 `color-scheme`，使表单控件与滚动条跟随主题。

**首帧防闪**：脚本先为 `<html>` 添加 `theme-lock` 类，由样式表在该类存在时抑制过渡；主题写入后，连续两帧 `requestAnimationFrame` 再移除该类。作用是避免浏览器以默认色渲染首帧、随后瞬间切换所造成的闪白。

**手动切换**：双击「星玖工作室出品」标题，翻转 `data-theme` 并同步更新 `<meta name="theme-color">`，使移动端浏览器地址栏颜色一致。手动切换后不写入本地存储，刷新后重新按系统偏好判定——这是刻意选择：官网以「跟随系统」为默认体验，不额外引入状态持久化。

**过渡**：主题切换通过 CSS 自定义属性在 0.5s 内渐变，覆盖背景、卡片、渐变文字、光晕、拖尾、烟花与底部星星。

**色彩令牌**：所有颜色集中在 `:root` 与 `[data-theme="dark"]` 两组自定义属性中，包括背景（亮色 `#E8EEFA` / 暗色 `#0E0E13`）、卡片、主文字、次级文字、强调色（亮色 `#4A6CF7` / 暗色 `#6361DC`）、卡片光晕、边框渐变、点阵与页脚色。页面内不存在硬编码色值，新增元素只需引用变量即可自动适配双主题。

### 3.2 设备适配与问候语

**判定阈值**：

| 设备类型 | 判定条件 | 显示文案 |
|---|---|---|
| 手机 | 视口宽度 < 768px | Hi, I'm **Ntars**（个人模式） |
| 平板 | 768px ≤ 视口宽度 ≤ 1180px 且具备触摸能力 | 横屏显示工作室模式，竖屏显示个人模式 |
| 桌面 | 其余情况 | Hi, We're **Ntarstudio**（工作室模式） |

平板判定同时要求 `ontouchstart in window` 或 `navigator.maxTouchPoints > 0`，避免大窗口桌面浏览器被误判为平板。平板端监听 `resize` 与 `orientationchange`（后者延迟 200ms 处理，等待系统完成旋转），转屏时自动切换模式；因模式已由方向决定，平板端禁用点击切换，防止手动状态与方向判定相互覆盖。

**切换动画**：先添加 `fade-out`（300ms），动画结束后替换文案，再添加 `fade-in`（300ms），期间以 `isAnimating` 标志防止连续点击造成状态错乱。

**打字效果**：由 Typed.js 驱动，循环播放两行文案 `>_ Remember what is important` 与 `>_ Forget what is painful`，参数为 `typeSpeed: 50`、`backSpeed: 20`、`startDelay: 300`、`loop: true`、`showCursor: false`。光标关闭是刻意选择：页面已有背景粒子与拖尾，再叠加闪烁光标会破坏整体的安静感。

### 3.3 项目卡片

**布局**：`.link-card-list` 使用 `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))`，间距 16px，最大宽度 968px，页面居中。两张卡片在桌面端等宽两列，窄屏自动降为一列，无需额外媒体查询。

**光晕交互**：`app.min.js` 在 `mousemove` 时读取指针相对卡片的坐标，写入 `--mouse-x` / `--mouse-y` 两个 CSS 变量；卡片的 `::before` 以 `radial-gradient(400px circle at var(--mouse-x) var(--mouse-y), ...)` 绘制跟随光晕，`.show` 层绘制悬停填充。指针移出卡片范围时将 `.show` 透明度置 0，避免光晕残留在卡片边缘。该实现不产生额外的 DOM 结构，也不触发布局重排。

**结构一致性**：两张卡片使用相同的 DOM 结构与箭头图标（内联 SVG，`currentColor` 着色），仅文案、链接与可选图标不同——元鸣 Ondra 卡片在箭头前放置 40×40 的项目图标 `assets/img/dpet-icon.svg`（取自自有项目 NT-Dpet 的站点图标，`.link-card-item img` 样式原生支持）。这样做的目的是保证任意一张卡片的状态变更不会造成版式差异。

**可访问性**：卡片外层为 `<a>`，新窗口打开时均带 `rel="noopener noreferrer"`，防止目标页面通过 `window.opener` 反向控制本页。

### 3.4 联系我们弹窗

**入口**：右上角固定文字按钮 `#contact-card`，`position: fixed`，带 `role="button"`、`tabindex="0"`、`aria-haspopup="dialog"`、`aria-controls`，支持鼠标点击与键盘 `Enter` / `空格`。

**关闭方式**：点击遮罩、点击面板右上角关闭按钮、按 `Esc`，三种方式等价。

**滚动锁定与位移补偿**：打开时计算 `window.innerWidth - document.documentElement.clientWidth` 得到滚动条宽度，为 `body` 补等宽 `padding-right`，再设 `overflow: hidden`。若不做补偿，滚动条消失会导致页面内容整体右移，产生横向跳动。

**关闭时序**：关闭时不立即解锁滚动，而是等待面板的 `opacity` 过渡结束（监听 `transitionend`，并以 500ms 定时器兜底，覆盖 `prefers-reduced-motion` 跳过动画的情况）后再隐藏容器并恢复滚动。退场动画只过渡 `opacity`，不参与 `transform`，否则面板会朝其变换原点方向移动，观感上像被「吸」向角落。

**内容分组**：社交平台（GitHub、爱发电、哔哩哔哩）为外链，新窗口打开；联系方式（邮箱、QQ、微信）为纯文本，点击复制到剪贴板。

**剪贴板实现**：`security.js` 全局拦截了 `selectstart` 与 `copy` 事件，纯文本项又无法通过 `<a>` 跳转，因此复制功能绕过事件层，直接调用 `navigator.clipboard.writeText()` 写入。写入成功显示「已复制」，失败显示「复制失败」，1.2s 后还原原文案；同一项在反馈期间通过 `data-copied` 标记去重，防止连续点击导致定时器叠加。

**无障碍**：面板为 `role="dialog"`、`aria-modal="true"`、`aria-labelledby` 指向标题；打开时焦点移至关闭按钮，关闭时归还给触发前的元素；所有可交互项均支持键盘操作。

### 3.5 视觉特效

| 效果 | 文件 | 触发方式 | 主题适配 |
|---|---|---|---|
| 烟花粒子 | `firework.js` | 点击 / 触摸 | 读取 CSS 变量决定粒子色 |
| 鼠标拖尾 | `trail.js` | 指针移动 | 亮色为深色拖尾，暗色为浅色拖尾 |
| 背景粒子 | `bg.js` | 常驻，随指针排斥 | 节点与连线颜色随主题切换 |
| 卡片光晕 | `app.min.js` | 卡片悬停 | 由 `--magical-glow` 控制 |
| 底部装饰 | `base.css` | 常驻 | 光晕、三层上升星星（1px / 2px / 1px）、地球圆 |

脚本按依赖顺序加载：`security.js` → `app.min.js` → `anime.js` → `firework.js` → `trail.js` → `bg.js`。烟花依赖 anime.js 的时间轴能力，因此必须在其后加载；安全模块优先级最高，先于其他脚本执行。

### 3.6 安全防护

`security.js` 提供以下拦截：禁止文本选中、复制、剪切；禁止右键菜单与拖拽；屏蔽开发者工具与查看源码相关快捷键（F12、`Ctrl+Shift+I/C`、`Ctrl+U/S/P`、`Ctrl+A`）；隐藏链接悬停时的地址提示；监测 `body` 被清空的情况并刷新页面；检测开发者工具开启时在控制台输出提示。

**能力边界（重要）**：上述措施仅提高随手复制的门槛，不构成任何形式的内容保护或加密。前端代码与页面内容对访问者始终可见，任何安全脚本都无法改变这一点。需要保密的信息不得置于前端。

**内容安全策略**：页面通过 `<meta http-equiv="Content-Security-Policy">` 声明资源白名单。`default-src` 与 `script-src` 仅允许 `'self'`、内联脚本与 `https://unpkg.com`；`img-src` 仅允许 `'self'` 与 `data:`；`frame-src` 与 `object-src` 为 `'none'`，禁止嵌入框架与插件；`connect-src` 限制为 `'self'`，页面不发起任何外部接口请求。同时声明 `X-Content-Type-Options: nosniff`、`X-Frame-Options: DENY`、`X-XSS-Protection` 与 `referrer: no-referrer`，其中 `no-referrer` 可避免访问者从本页跳转至第三方时泄露来源地址。

### 3.7 PWA

**清单**：`manifest.json` 声明 `display: standalone`、`display_override: ["standalone", "minimal-ui"]`、`orientation: portrait-primary`、`lang: zh-CN`、分类 `lifestyle` / `utilities`，并提供 192、512 与 SVG 三种图标。

**缓存策略**：`sw.js` 采用「缓存优先 + 后台更新」。命中缓存时立即返回，同时在后台请求网络并将新响应写回缓存；未命中时走网络，成功响应写入缓存；网络失败且请求为 HTML 时回退到 `index.html`，其他资源返回 503。

**缓存纪律**：`CACHE_NAME` 当前为 `ntarstudio-v4`。任何被预缓存列表覆盖的资源（含通过 CDN 引入的 Typed.js）发生变更后，必须同步提升该版本号，否则访问者会持续命中旧缓存。`install` 阶段调用 `skipWaiting()`，`activate` 阶段删除所有非当前版本的缓存并调用 `clients.claim()` 立即接管页面。

**安装**：监听 `beforeinstallprompt` 并保存事件对象，当前依赖浏览器原生安装界面，未自定义安装按钮。以 `display-mode: standalone` 判断是否已作为应用运行。

### 3.8 SEO 与结构化数据

| 项 | 内容 |
|---|---|
| `description` | 覆盖品牌名与两个在营项目的定位、状态与域名 |
| `keywords` | 品牌词、项目代号、产品类型词；已移除全部下线项目词 |
| Open Graph | `og:type` / `title` / `description` / `url` / `site_name` / `locale` |
| canonical | `https://www.ntars.cn/`，与 `og:url` 保持一致 |
| JSON-LD | Schema.org `Organization`，含 `name`、`alternateName`、`url`、`description`、`sameAs`（GitHub、哔哩哔哩、爱发电） |
| robots | `index, follow, noarchive, max-image-preview:large`；`noarchive` 阻止搜索引擎保存快照 |
| 站点验证 | 百度通过 `baidu_verify_codeva-C4tp7NQbk5.html` 与 `baidu-site-verification` 元标记双重验证 |

JSON-LD 只保留组织级 `url`（官网自身），两个在营项目的正式地址在项目卡片与状态表中呈现；元鸣 Ondra 的官网 `ai.ntars.cn` 已上线，其地址以卡片直链形式可被搜索引擎正常抓取；`x.ntars.cn` 未上线，故不出现在任何元信息中。

### 3.9 页脚与备案

页脚位于页面内容之后、底部装饰层之前，包含两行：备案号（链接至 `beian.miit.gov.cn`，新窗口打开）与版权行 `© 2024 - 2026 Ntarstudio. All Rights Reserved.`。备案号使用独立样式类，不随主题切换改变语义，仅在颜色上跟随主题。

---

## 四、技术栈与开源组件

### 4.1 技术构成

| 层 | 选型 | 说明 |
|---|---|---|
| 结构 | 原生 HTML5 | 单文件，语义标签 + `role` 补充 |
| 样式 | 原生 CSS（自定义属性 + Grid + Flexbox） | 无预处理器参与构建，无 CSS 框架 |
| 交互 | 原生 JavaScript（ES5 语法为主） | 无框架、无模块打包，直接 `<script>` 加载 |
| 动画 | anime.js v2.0.2 | 仅烟花粒子使用 |
| 字体 | 系统字体栈 | 不加载任何网络字体 |
| 图标 | 自研 SVG / PNG | 不使用图标库 |
| 离线 | Service Worker + Web App Manifest | 缓存优先策略 |
| 部署 | EdgeOne Pages | 静态托管，无服务端运行时；推送 `main` 后 EdgeOne 自动发布，本项目不使用 GitHub Pages 或腾讯云 COS |

页面不使用 jQuery、Vue、React 或任何 UI 组件库；不使用 Tailwind 等原子化 CSS 框架；不使用构建工具（Vite / Webpack / Rollup）；不使用 npm 依赖。因此仓库内不存在 `node_modules`、`package.json` 或锁文件。

### 4.2 第三方组件清单

以下为页面实际使用或分发的全部第三方内容。完整版权声明与再分发义务见 [`NOTICE`](NOTICE)。

| # | 组件 | 版本 | 版权人 | 许可 | 引入方式 | 用途 |
|---|---|---|---|---|---|---|
| 1 | asorn/asorn-open | — | asorn | Apache-2.0 | 源码派生 | 页面结构与基础布局的初始底座 |
| 2 | anime.js | v2.0.2 | Julian Garnier (2017) | MIT | 整文件内嵌 `assets/js/anime.js` | 烟花粒子的时间轴与缓动 |
| 3 | Typed.js | 2.0.16 | Matt Boldt（年份以上游 LICENSE 为准） | MIT | unpkg CDN + Service Worker 预缓存 | 问候区打字效果 |

**派生关系说明**：本项目在 asorn/asorn-open 的基础上修改、扩展并重新设计了界面与结构，属修改后的衍生作品。依据 Apache-2.0 第 4 条，已保留原版权声明、许可全文（`LICENSE-Apache-2.0.txt`）与变更说明（`NOTICE`）。当前页面实际加载的 `base.css` 中，卡片光晕（`.magical`）与部分布局断点源自上游；联系我们弹窗、双主题令牌、页脚与响应式细节为本项目新增或重写。

**许可义务**：

- **MIT（anime.js、Typed.js）**：分发时必须保留原版权声明与许可声明。`anime.js` 文件头已保留 `Released under the MIT license` 声明，不得删除；`Typed.js` 通过 CDN 引入，若改为本地内嵌，须一并附上其许可文本。
- **Apache-2.0（asorn/asorn-open）**：分发衍生作品时须保留版权声明、许可全文，并对修改过的文件作出说明。本项目通过 `NOTICE` 与 `LICENSE-Apache-2.0.txt` 履行该义务。

### 4.3 未使用项（排除声明）

为避免误认，以下内容**未被本项目使用**：

| 项 | 状态 |
|---|---|
| 第三方网络字体（Google Fonts 等） | 未使用。字体栈为系统字体，无外部字体请求 |
| 第三方图标库（Font Awesome、iconfont 等） | 未使用。图标为自研 SVG / PNG |
| 前端框架与 UI 组件库 | 未使用 |
| 统计与埋点脚本（Google Analytics、百度统计等） | 未使用 |
| 广告、评论、客服组件 | 未使用 |
| Cookie 与本地存储写入 | 未使用（主题状态不持久化） |
| 后端接口与数据库 | 未使用 |

### 4.4 商标与名称声明

「星玖工作室」「Ntarstudio」「玄玖灵犀」「Xael」「NT-Xhex」「元鸣」「Ondra」「玄宠」「NT-Dpet」「玄玖大模型」「NT-Sine」等名称与标识归星玖工作室所有。MIT 与 Apache-2.0 仅授予代码权利，不授予商标使用权，也不授予暗示原作者背书的使用方式。

页面与文档中提及的第三方名称（GitHub、哔哩哔哩、爱发电、DeepSeek、Qwen 等）归各自权利人所有，仅用于说明跳转目标或兼容对象，不表示任何关联或背书。

---

## 五、版权与许可

### 5.1 本项目许可

| 范围 | 许可 | 全文 |
|---|---|---|
| 自研代码（页面结构、样式、脚本及后续改动） | MIT | [`LICENSE`](LICENSE) |
| 派生自 asorn/asorn-open 的部分 | Apache License 2.0 | [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| 品牌名称、Logo、界面设计 | 保留所有权利 | 见 `NOTICE` |

### 5.2 再分发要求

再分发本项目时须一并保留：

1. `NOTICE`（版权与第三方声明）；
2. `LICENSE`（MIT 全文）；
3. `LICENSE-Apache-2.0.txt`（Apache-2.0 全文）；
4. `assets/js/anime.js` 文件头原有的版权与许可声明；
5. `assets/css/base.css` 中源自上游的样式所对应的版权说明（已记录于 `NOTICE`）。

不得删除或篡改第三方文件的版权声明与许可声明。修改版不得使用原项目品牌标识，也不得暗示获得原作者背书。

---

## 六、开发与运维

### 6.1 本地运行

```bash
python3 -m http.server 8000
# 访问 http://localhost:8000
```

Service Worker 仅在 `localhost` 或 HTTPS 环境下注册，`file://` 协议不支持。页面无构建步骤，修改后刷新即可生效。

### 6.2 修改自查清单

1. 两张卡片的标题、描述、链接与在营项目的真实状态一致；
2. `description`、`keywords`、`og:*`、JSON-LD、`canonical` 与页面正文口径一致；
3. 预缓存资源发生变更时，`sw.js` 中的 `CACHE_NAME` 已升版；
4. 亮色与暗色两套主题下均已检查（双击标题切换）；
5. 手机（< 768px）、平板（768–1180px）与桌面三种宽度下均无文字截断或布局溢出；
6. 弹窗打开时背景不滚动、关闭后滚动位置不跳动；
7. 新增任何第三方资源时，已在 `NOTICE` 与本文 4.2 节登记来源、版权人、许可与修改情况。

### 6.3 部署

| 方式 | 状态 | 说明 |
|---|---|---|
| EdgeOne Pages | **当前线上方式（唯一）** | 主域名 `www.ntars.cn` 指向 EdgeOne Pages，推送 `main` 后自动发布；本项目不含任何 workflow 文件，不触发 GitHub Actions |

### 6.4 发布纪律

- 页面内容变更后，必须同步检查 `sw.js` 缓存版本，避免访问者长期停留在旧版本；
- 子项目状态发生变化（上线、下线、域名变更）时，须同时更新两张卡片、元信息与本文档的状态表；
- 已下线项目不得以任何形式重新出现在页面、关键词或结构化数据中；
- 新增第三方组件前，先确认其许可与 Apache-2.0 / MIT 兼容，并在 `NOTICE` 登记后方可提交。

---

## 七、变更记录

| 日期 | 内容 |
|---|---|
| 2026-10-27 | 项目口径更新：三张卡片调整为两张——玄玖灵犀 Xael（产品已上线 v4.3.0，官网 `x.ntars.cn` 未解析、筹备中，暂挂仓库地址）与元鸣 Ondra（官网 `ai.ntars.cn` 已上线，软件未发布）；Ondra 卡片使用 NT-Dpet 图标素材（assets/img/dpet-icon.svg）；移除已并入 Ondra 口径的 NT-Sine 独立卡片与 pet.ntars.cn 链接；meta、Open Graph、JSON-LD 同步；缓存版本升至 `ntarstudio-v6`；NOTICE 更新商标清单、外链与素材登记 |
| 2026-10-23 | 项目信息纠正：三张卡片调整为 NT-Xhex、NT-Dpet、NT-Sine；移除已下线的 NT-Know 与 NT-List；同步 meta、Open Graph、JSON-LD 与 canonical；补充 `NOTICE` 中 anime.js 与 Typed.js 的版权与许可声明；缓存版本升至 `ntarstudio-v4`；按实测修正部署说明（GitHub Pages 未启用） |
| 2026-10-20 | 许可调整：自研代码改为 MIT，派生部分保留 Apache-2.0 全文与致谢 |
| 2026-10-20 | 许可合规：`LICENSE` 补全 Apache-2.0 官方全文，新增 `NOTICE` 保留上游出处 |
| 2026-10-15 | 图标更换为圆角方形「N+T」词标 |
| 2026-10-15 | 初始提交：星玖工作室官网主页 |

---

## 附：联系方式

| 分类 | 名称 | 内容 |
|---|---|---|
| 官方网站 | 星玖工作室官网 | https://www.ntars.cn/ |
| 社交平台 | GitHub | https://github.com/ntars |
| 社交平台 | 爱发电 | https://afdian.com/a/ntars |
| 社交平台 | 哔哩哔哩 | https://space.bilibili.com/499925438 |
| 联系方式 | 邮箱 | ntarsx@163.com |
| 联系方式 | QQ | 3933361415 |
| 联系方式 | 微信 | Ntarsv |
