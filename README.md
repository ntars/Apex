**简体中文** | [English](README.en.md)

# Apex

星玖工作室（Ntarstudio）的官网主页与项目入口，代号 Apex。一个 HTML 文件、一份样式表、几个原生脚本，没有框架、没有构建、没有后端。

| | |
|---|---|
| 代号 | Apex |
| 线上 | <https://www.ntars.cn/> |
| 仓库 | <https://github.com/ntars/Apex> |
| 形态 | 单页静态站点，可安装为 PWA |
| 体积 | `index.html` + `assets/css/base.css` + 5 个自研脚本 + 1 个第三方动画库 + `sw.js` |
| 许可 | 自研部分 MIT，派生部分 Apache-2.0 |
| 备案 | 蜀ICP备2026027050号 |
| 版权 | Copyright (c) 2024–2026 星玖工作室 Ntarstudio |

## 这个站点解决什么

访客打开首页，应当立即获得三个答案：这是谁、他们在做什么、去哪里看。

因此站点的全部职责只有三项：**建立品牌识别**（首屏把「星玖工作室 / Ntarstudio / Ntars」三个称呼对应起来）、**导向开源项目**（两张卡片直连正式地址）、**信息如实**（未上线、已下线的信息一律不出现在页面、关键词、结构化数据里）。

本站不做的事同样明确：没有账号、没有表单、没有 Cookie、没有统计埋点、没有广告、没有后端接口。所有内容都在 `index.html` 里硬编码，改一行文字就是一次提交，不经过任何 CMS。

## 开源项目与状态口径

| 项目 | 是什么 | 状态 | 去哪里 |
|---|---|---|---|
| **玄玖灵犀 Xael** | 本地离线的术数文献库，微信小程序与公众号同名 | 产品已上线 | [x.ntars.cn](https://x.ntars.cn/) |
| **元鸣 Ondra** | 可一键部署、高度自定义的 AI 陪伴体 | 产品内测中 | [ai.ntars.cn](https://ai.ntars.cn/) |

状态标注遵守一条规矩：**官网状态与产品状态分开说**。两者不等价——官网在跑不代表软件能装，软件在跑也不代表官网能开。

- Xael：产品已上线，微信小程序与公众号同名可搜到，入口统一写官网 `x.ntars.cn`；
- Ondra：产品内测中，官网 `ai.ntars.cn` 提供介绍与内测入口，未公测这一点不与「已上线」混写。

判断依据以你提供的现状描述为准：卡片文案与元信息同步采用同一口径，未上线的域名不出现在任何位置。

## 页面结构与代码组织

页面自上而下五块：问候区、分割线、项目区、右上角联系我们入口、页脚。外加四个常驻叠加层（烟花 canvas、拖尾 canvas、背景粒子 canvas、底部装饰）。没有路由，没有虚拟 DOM，滚动由浏览器原生完成。

```
Apex/
├── index.html                 # 结构 + 元信息 + 四段内联脚本
├── manifest.json              # PWA 清单
├── sw.js                      # Service Worker：预缓存、缓存优先、后台刷新、旧缓存清理
├── LICENSE                    # MIT 全文
├── LICENSE-Apache-2.0.txt     # Apache-2.0 全文（asorn 派生部分）
├── NOTICE                     # 版权与第三方声明
├── 开源方案扫描.md             # 三个项目的开源方案盘点
├── baidu_verify_codeva-C4tp7NQbk5.html   # 百度站点验证
├── tencent-cloud-config.yml   # 腾讯云托管参考配置（当前不用）
├── README.md / README.en.md
└── assets/
    ├── css/
    │   ├── base.css           # 唯一被加载的样式表
    │   ├── base.scss          # 与 base.css 对应的样式源
    │   └── base.min.css       # base.css 的压缩产物
    ├── js/
    │   ├── security.js        # 禁用选中/复制/右键/快捷键，篡改监测
    │   ├── app.min.js         # 卡片光晕：指针坐标 → CSS 变量
    │   ├── anime.js           # anime.js v2.0.2（第三方，MIT，不修改）
    │   ├── firework.js        # 烟花粒子
    │   ├── trail.js           # 指针拖尾
    │   └── bg.js              # 背景粒子与连线
    └── img/                   # 自研 N+T 词标与 PWA 图标
```

**为什么脚本分六个文件而不是一个**：每个文件只负责一件事，出现问题时可以单独移除。例如不需要拖尾效果时，删除 `trail.js` 的一行引用即可，其余五个文件不受影响。文件之间唯一的硬依赖是 `firework.js` 依赖 `anime.js`，因此加载顺序固定为 `security → app.min → anime → firework → trail → bg`。

**为什么卡片是配置驱动的**：卡片内容写在 `index.html` 内的 `PROJECTS` 数组里（标题、描述、链接、可选图标四个字段），箭头图标只定义一次。改项目状态是改一行数据，不是改一段 HTML——避免「改了卡片忘了改元信息」和「两张卡片结构漂移」这两类历史问题。

## 关键实现

### 主题：跟随系统，手动可覆盖，刷新不记住

`<head>` 里同步执行的内联脚本读 `prefers-color-scheme`，媒体查询不可用时按本地时间兜底（6:00–18:00 亮色，其余暗色），结果写入 `<html data-theme>` 与 `color-scheme`。双击「星玖工作室出品」可手动翻转，并同步 `<meta name="theme-color">`，让移动端地址栏同色。

手动状态不写 localStorage——这是故意的。官网的默认体验是跟随系统，多存一个开关就多一处需要解释的状态。刷新即回到系统偏好。

**首帧不闪白**：脚本先给 `<html>` 加 `theme-lock`，样式表在该类下抑制全部过渡；主题落定后连续两帧 `requestAnimationFrame` 才移除。少了这两帧，浏览器会先用默认色画一帧再跳变，暗色系统上就是一下白闪。

颜色全部收敛在 `:root` 与 `[data-theme="dark"]` 两组自定义属性里，页面内不写硬编码色值；新增元素引用变量即可自动双主题。过渡由 `html:not(.theme-lock)` 下的统一 0.5s 规则接管。

### 问候语：三种设备，两种腔调

| 设备 | 判定 | 显示 |
|---|---|---|
| 手机 | 视口 < 768px | Hi, I'm **Ntars** |
| 平板 | 768–1180px 且具备触摸 | 横屏工作室模式，竖屏个人模式 |
| 桌面 | 其余 | Hi, We're **Ntarstudio** |

平板判定额外要求 `ontouchstart in window` 或 `navigator.maxTouchPoints > 0`，否则大窗口桌面浏览器会被误判。平板转屏监听 `resize` 与 `orientationchange`（后者延迟 200ms，等系统转完），模式由方向决定，因此平板端禁用点击切换——否则手动状态会和方向判定互相覆盖。

切换时先 `fade-out`（300ms）、换文案、再 `fade-in`，用 `isAnimating` 标志挡住连点。

打字效果由 Typed.js 驱动，循环 `>_ Remember what is important` 与 `>_ Forget what is painful`，`typeSpeed: 50` / `backSpeed: 20` / `startDelay: 300` / `loop: true` / `showCursor: false`。关闭光标是刻意选择：页面已有背景粒子与拖尾，再叠加闪烁光标会破坏整体的安静感。

### 项目卡片：光晕跟着指针走

`.link-card-list` 是 `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))`，间距 16px，最大宽 968px 居中。桌面两列、窄屏一列，不需要写媒体查询。

`app.min.js` 在 `mousemove` 时算出指针相对卡片的坐标，写进 `--mouse-x` / `--mouse-y`；卡片 `::before` 用 `radial-gradient(400px circle at var(--mouse-x) var(--mouse-y), …)` 画出跟随的光晕。指针移出卡片范围时把 `.show` 层透明度归零，防止光晕卡在边缘。整个过程不动 DOM 结构、不引发布局重排。

两张卡片 DOM 完全同构，只有文案与链接不同，图标字段为可选能力（`icon: null` 时不渲染 `<img>`）。同构是为了让任一卡片的状态变更不产生版式差异。

卡片外层是 `<a>`，新窗口打开一律带 `rel="noopener noreferrer"`，避免目标页面通过 `window.opener` 反控本页。

### 联系我们：弹窗滚动的两个易错点

入口是右上角固定文字按钮 `#contact-card`（`role="button"`、`tabindex="0"`、`aria-haspopup="dialog"`、`aria-controls`），支持点击与键盘。关闭方式三种等价：遮罩、关闭按钮、`Esc`。

**易错点一：滚动条消失导致页面右移**。打开时计算 `window.innerWidth - document.documentElement.clientWidth` 得到滚动条宽度，补到 `body` 的 `padding-right` 上再设 `overflow: hidden`。缺少补偿时，背后的内容会随滚动条消失整体位移。

**易错点二：退场动画将面板拉向变换原点**。关闭时不立即解锁滚动，而是等待面板 `opacity` 过渡结束（监听 `transitionend`，另以 500ms 定时器兜底，覆盖 `prefers-reduced-motion` 跳过动画的情况）再隐藏容器并恢复滚动。退场仅过渡 `opacity`，不修改 `transform`——否则面板会朝变换原点移动，观感上像被吸附。

内容分两组：社交平台（GitHub、爱发电、哔哩哔哩）走外链；联系方式（邮箱、QQ、微信）是纯文本，点击复制。复制绕过事件层直接调 `navigator.clipboard.writeText()`（因为 `security.js` 全局拦了 `selectstart` 与 `copy`），成功显示「已复制」、失败显示「复制失败」，1.2s 后还原，用 `data-copied` 标记去重防止连续点击叠加定时器。

### 视觉特效与安全防护

| 效果 | 文件 | 触发 | 主题适配 |
|---|---|---|---|
| 烟花 | `firework.js` | 点击 / 触摸 | 粒子色随 `data-theme` 切换 |
| 拖尾 | `trail.js` | 指针移动 | 亮色深拖尾、暗色浅拖尾 |
| 背景粒子 | `bg.js` | 常驻，指针排斥 | 节点与连线颜色随主题 |
| 卡片光晕 | `app.min.js` | 卡片悬停 | `--magical-glow` |
| 底部装饰 | `base.css` | 常驻 | 光晕 + 三层上升星星 + 地球圆 |

`security.js` 拦截选中、复制、剪切、右键、拖拽、F12 与查看源码类快捷键，隐藏链接悬停地址，监测 `body` 被清空后刷新，检测开发者工具开启时在控制台输出提示。

需要说清楚的是：**这些措施只提高随手复制的门槛，不构成任何内容保护**。前端代码对访问者始终可见，任何脚本都改变不了这一点。需要保密的东西不要放在前端。

页面用 `<meta http-equiv="Content-Security-Policy">` 声明白名单：`default-src` / `script-src` 仅 `'self'`、内联与 `https://unpkg.com`；`img-src` 仅 `'self'` 与 `data:`；`frame-src` / `object-src` 为 `'none'`；`connect-src` 仅 `'self'`（页面不发起外部接口请求）。另带 `nosniff`、`X-Frame-Options: DENY`、`referrer: no-referrer`。

### PWA 与缓存纪律

`manifest.json` 声明 `display: standalone`、`display_override: ["standalone", "minimal-ui"]`、`orientation: portrait-primary`、`lang: zh-CN`、分类 `lifestyle` / `utilities`，图标提供 192、512 与 SVG 三种。

`sw.js` 走「缓存优先 + 后台更新」：命中缓存先返回，同时后台请求并把 200 响应写回；未命中走网络；网络失败且请求 HTML 时回退 `index.html`，其他资源返回 503。`install` 阶段 `skipWaiting()`，`activate` 阶段删除非当前版本缓存并 `clients.claim()`。

**`CACHE_NAME` 当前为 `ntarstudio-v6`。** 只要动了预缓存清单里的任何资源（包括通过 CDN 引入的 Typed.js），就必须升版本号，否则回访用户会长期停在旧缓存上——这是本项目最容易忘、后果最明显的一步。

### SEO 与结构化数据

| 项 | 内容 |
|---|---|
| `description` | 品牌名 + 两个开源项目的定位与状态 |
| `keywords` | 品牌词、项目代号、产品类型词；不含任何下线项目 |
| Open Graph | `type` / `title` / `description` / `url` / `site_name` / `locale` |
| canonical | `https://www.ntars.cn/`，与 `og:url` 一致 |
| JSON-LD | Schema.org `Organization`：`name`、`alternateName`、`url`、`description`、`sameAs`（GitHub、哔哩哔哩、爱发电） |
| robots | `index, follow, noarchive, max-image-preview:large` |
| 验证 | 百度 `baidu_verify_codeva-C4tp7NQbk5.html` + `baidu-site-verification` 元标记 |

JSON-LD 只放组织级 `url`；项目地址由卡片直链承担，与当前项目状态口径一致。

页脚两行：备案号（链到 `beian.miit.gov.cn`，新窗口）与 `© 2024 - 2026 Ntarstudio. All Rights Reserved.`。

## 技术栈

| 层 | 选型 |
|---|---|
| 结构 | 原生 HTML5，语义标签 + `role` 补充 |
| 样式 | 原生 CSS：自定义属性 + Grid + Flexbox，无预处理器参与构建 |
| 交互 | 原生 JavaScript（以 ES5 语法为主，便于老浏览器直接执行） |
| 动画 | anime.js v2.0.2，仅烟花粒子使用 |
| 字体 | 系统字体栈，不加载网络字体 |
| 图标 | 自研 SVG / PNG |
| 离线 | Service Worker + Web App Manifest |
| 部署 | EdgeOne Pages |

不使用 jQuery / Vue / React / UI 组件库，不使用 Tailwind 类原子化框架，不使用 Vite / Webpack / Rollup，不使用 npm 依赖——所以仓库里没有 `node_modules`、`package.json` 与锁文件。

### 第三方组件

| 组件 | 版本 | 版权人 | 许可 | 引入方式 | 用途 |
|---|---|---|---|---|---|
| asorn/asorn-open | — | asorn | Apache-2.0 | 源码派生 | 初始底座 |
| anime.js | v2.0.2 | Julian Garnier (2017) | MIT | 整文件内嵌 `assets/js/anime.js` | 烟花时间轴与缓动 |
| Typed.js | 2.0.16 | Matt Boldt | MIT | unpkg CDN + SW 预缓存 | 问候语打字 |

**派生关系**：本项目在 asorn/asorn-open 基础上修改、扩展并重新设计了界面与结构，属衍生作品。依 Apache-2.0 第 4 条已保留原版权声明、许可全文（`LICENSE-Apache-2.0.txt`）与变更说明（`NOTICE`）。现行 `base.css` 中 `.magical` 卡片光晕与部分布局断点源自上游，联系我们弹窗、双主题令牌、页脚与响应式细节为本项目新增或重写。

**MIT 义务**：分发时保留原版权与许可声明。`anime.js` 文件头的 `Released under the MIT license` 不得删除；Typed.js 走 CDN，若改本地内嵌须附许可文本。

### 明确未使用

第三方网络字体 · 第三方图标库 · 前端框架与 UI 库 · 统计与埋点 · 广告与评论客服组件 · Cookie 与本地存储写入 · 后端接口与数据库。以上均无。

### 名称与商标

「星玖工作室」「Ntarstudio」「玄玖灵犀」「Xael」「NT-Xhex」「元鸣」「Ondra」「玄玖大模型」「NT-Sine」等名称与标识归星玖工作室所有。MIT 与 Apache-2.0 只给代码权利，不给商标权，也不给「暗示获得背书」的权利。文档中出现的第三方名称（GitHub、哔哩哔哩、爱发电、DeepSeek、Qwen 等）归各自权利人，仅用于说明跳转目标或兼容对象。

## 许可与再分发

| 范围 | 许可 |
|---|---|
| 自研代码（结构、样式、脚本及后续改动） | MIT，见 [`LICENSE`](LICENSE) |
| 派生自 asorn/asorn-open 的部分 | Apache-2.0，见 [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| 品牌名称、Logo、界面设计 | 保留所有权利，见 [`NOTICE`](NOTICE) |

再分发须一并保留：`NOTICE`、`LICENSE`、`LICENSE-Apache-2.0.txt`、`assets/js/anime.js` 文件头的版权与许可声明。不得删除或篡改第三方版权声明；修改版不得使用原品牌标识，也不得暗示获得背书。

## 本地运行与部署

```bash
python3 -m http.server 8000
# 打开 http://localhost:8000
```

没有构建步骤，改完刷新即生效。Service Worker 只在 `localhost` 或 HTTPS 下注册，`file://` 不支持。

**部署只有一条路**：推 `main` → EdgeOne Pages 自动发布，主域名 `www.ntars.cn` 指向该站。仓库不含任何 workflow 文件，不触发 GitHub Actions，也不走腾讯云 COS。

### 改动前自查

1. 两张卡片的标题、描述、链接与项目真实状态一致，未上线的域名不出现在任何位置；
2. `description`、`keywords`、`og:*`、JSON-LD、`canonical` 与正文口径同步；
3. 动了预缓存里的资源，`sw.js` 的 `CACHE_NAME` 已升版；
4. 亮色与暗色两套主题都看过（双击标题切换）；
5. 手机（< 768px）、平板（768–1180px）、桌面三档宽度下无截断与溢出；
6. 弹窗打开时背景不滚、关闭后滚动位置不跳；
7. 新增第三方资源已在 `NOTICE` 与本文「第三方组件」表登记来源、版权人、许可与修改情况。

### 发布纪律

- 内容变更后必须检查 `CACHE_NAME`，这是最容易漏的一步；
- 子项目状态变化（上线、下线、换域名）时，卡片、元信息、本文档状态表三处同改；
- 已下线项目不得以任何形式回到页面、关键词或结构化数据；
- 新增第三方组件前先确认许可与 MIT / Apache-2.0 兼容，并在 `NOTICE` 登记后才提交。

## 联系方式

| | |
|---|---|
| 官网 | <https://www.ntars.cn/> |
| GitHub | <https://github.com/ntars> |
| 爱发电 | <https://afdian.com/a/ntars> |
| 哔哩哔哩 | <https://space.bilibili.com/499925438> |
| 邮箱 | ntarsx@163.com |
| QQ | 3933361415 |
| 微信 | Ntarsv |
