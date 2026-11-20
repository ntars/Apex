# 分层许可说明

> 本文件是人类可读的分层路由表。`LICENSE` 是 **MIT** 全文；
> `LICENSE-Apache-2.0.txt` 是 **Apache-2.0** 全文，它存在的原因是本仓库含上游派生部分，
> 不是装饰。GitHub 只按 `LICENSE` 识别仓库主许可，因此显示为 MIT；Apache-2.0 覆盖的
> 那一小块见下表。

本仓库以 **MIT 为主许可**，只有派生部分适用 **Apache License 2.0**。

Copyright (c) 2024–2026 星玖工作室 Ntarstudio

---

## 零、默认归属（先看这条）

**下表未列出的、由本项目编写的文件，一律适用根 [`LICENSE`](./LICENSE)，即 MIT。**

这条兜底规则是必须的。只写「本仓库是 MIT」而不列例外，读者无法判断
`assets/css/base.css` 到底归哪个许可——而那恰好是本仓库唯一有额外义务的文件。
需要相反结果的路径，必须显式写进下表。

---

## 一、分层映射

| 路径 | 许可 | 说明 |
|---|---|---|
| `index.html` | **MIT** | 页面结构与内联脚本（主题初始化、设备彩蛋、联系我们弹窗、PWA 注册） |
| `assets/js/security.js` `app.min.js` `firework.js` `trail.js` `bg.js` | **MIT** | 自研交互脚本 |
| `assets/css/base.scss` | **MIT** | 源文件，自研部分 |
| `assets/css/base.css` `assets/css/base.min.css` | **MIT + Apache-2.0（文件内混合）** | `.magical` 卡片光晕、布局断点等规则源自 asorn/asorn-open，受 Apache-2.0 约束；其余规则自研，MIT。见 §2 |
| `assets/img/` | **MIT** | 自研 N+T 词标、favicon 与 PWA 图标 |
| `sw.js` `manifest.json` | **MIT** | Service Worker 与 PWA 清单 |
| `baidu_verify_codeva-C4tp7NQbk5.html` `tencent-cloud-config.yml` | **MIT** | 站点校验与部署配置 |
| `README.md` `README_*.md` `NOTICE` `.gitignore` | **MIT** | 说明文档与仓库配置 |
| 品牌名称、Logo、界面设计 | **保留所有权利** | 不随代码许可授予 |

## 二、派生部分（Apache-2.0 的唯一来源）

本产品基于 [asorn/asorn-open](https://github.com/asorn/asorn-open)（Apache License 2.0）
修改而来，属修改后的衍生作品。派生规则集中在 `assets/css/base.css`：`.magical` 卡片光晕
与布局断点源自上游，其余视觉层（联系我们弹窗、双主题令牌、页脚、响应式细节）为本项目
新增或重写。

**这里的边界必须说清**：

1. `assets/css/base.css` 是**单文件内混合**——派生规则受 Apache-2.0，其余规则受 MIT。
   拿到文件的人不必把整份文件当 Apache-2.0 处理。
2. 但**不能因为整仓是 MIT 就把 `LICENSE-Apache-2.0.txt` 删掉**。Apache-2.0 第 4 条
   a（随附许可副本）、b（保留修改说明）、d（保留 NOTICE）三项义务随派生部分走，
   与仓库主许可无关，也不因「只占一个文件的一小段」而消失。
3. 若要彻底摆脱这层义务，唯一合法路径是重写掉这些规则、确认无残留后再移除 Apache 文本。
   在此之前，**「整仓单一 MIT」的表述是不准确的**。

## 三、第三方组件

| 组件 | 许可 | 内嵌位置 |
|---|---|---|
| anime.js v2.0.2（Julian Garnier） | MIT | `assets/js/anime.js`，整文件内嵌、未修改，文件头保留原声明 |
| Typed.js 2.0.16（Matt Boldt） | MIT | 经 unpkg CDN 引入，`sw.js` 预缓存，未修改 |

两项均为 MIT，与本仓库的 MIT 兼容；再分发时保留其版权与许可声明即可。
逐项披露见 [`NOTICE`](./NOTICE) 第三、四节。

## 四、商标

「星玖工作室」「Ntarstudio」「Apex」等名称、Logo 与界面设计归星玖工作室所有。
MIT 与 Apache-2.0 只授予**代码**权利，不授予商标权，也不授予「暗示获得原作者背书」的
权利。修改版请更换品牌标识，或明确标注为非官方版本。

## 五、再分发时须一并保留的文件

| 文件 | 依据 |
|---|---|
| `LICENSE`（MIT 全文） | MIT 正文「须包含上述版权声明与许可声明」 |
| `LICENSE-Apache-2.0.txt`（Apache-2.0 全文） | Apache-2.0 第 4 条 a 项，随派生部分 |
| `NOTICE` | Apache-2.0 第 4 条 d 项，随派生部分 |
| `assets/js/anime.js` 文件头的原有声明 | MIT（第三方） |

## 六、禁止引入 copyleft 组件

一个 GPL / LGPL / AGPL / MPL 组件一旦引入，整个项目将被要求以该 copyleft 许可分发。
引入新依赖前请核对 [`NOTICE`](./NOTICE) 的兼容性表。
