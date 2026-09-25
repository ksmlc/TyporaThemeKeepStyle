---
layout: theme
title: Lightmind
category: theme
homepage: https://github.com/SunMoonTrain/LightMindTheme
download: https://github.com/SunMoonTrain/LightMindTheme/releases/latest
built-in: false
author: SunMoonTrain
thumbnail: lightmind.png
typora-root-url: ../../
typora-copy-images-to: ../../media/theme/lightmind

---

# Lightmind

> 一个山林氛围的 Typora 主题 — 森林绿、米黄纸面、深海军蓝代码块。**浅色 + 暗色** 双版本。

---

为中英文混排长文写作设计的轻量 Typora 主题。正文用 **霞骛文楷 (LXGW WenKai)**，代码用 **JetBrains Mono**.

包含两个版本：

- **Lightmind**（`lightmind.css`）— 暖米色纸面 + 深森林强调色

  ![image-20260506032055867](/media/theme/lightmind/亮色主题.png)

- **Lightmind Dark**（`lightmind-dark.css`）— 深森林夜底 + 加亮绿色强调，代码块仍用同一深海军蓝

  ![image-20260506032135237](/media/theme/lightmind/暗色主题.png)

> ⚠️ **仅在 Windows（Typora 1.13.4）上测试通过。** macOS 与 Linux **未经测试**。理论上应该能正常工作（Typora 是 Electron 的，CSS 跨平台），但字体渲染、侧边栏度量、阴影表现可能略有差异。如有问题欢迎反馈或 PR。

## 预览

### 标题及正文

![image-20260506031837359](/media/theme/lightmind/标题和正文.png)

### 段落与行内格式

![image-20260506032249205](/media/theme/lightmind/段落与行内格式.png)

### 引用与警告块

![image-20260506032350537](/media/theme/lightmind/引用与警告块.png)

### 列表

![image-20260506032436214](/media/theme/lightmind/列表.png)

### 表格

![image-20260506032510951](/media/theme/lightmind/表格.png)

### 代码

![image-20260506032603502](/media/theme/lightmind/代码.png)

### 数学公式

![image-20260506032741002](/media/theme/lightmind/数学公式.png)

### Mermaid 图表

![image-20260506032844682](/media/theme/lightmind/Mermaid图表.png)

### 推荐字体

主题在不安装任何字体时也能用（会回退到系统字体），但为了达到设计意图，建议装：

- **[LXGW WenKai 霞骛文楷](https://github.com/lxgw/LxgwWenKai)** — 正文 / 中文
- **[JetBrains Mono](https://www.jetbrains.com/lp/mono/)** — 代码

两者都开源免费。

> **提示**：JetBrains Mono 不含中文字形，所以代码块里的中文会回退到霞骛文楷（楷体风格，不严格等宽）。如果你需要中文严格等宽对齐，建议装 **[Sarasa Mono SC 更纱黑体](https://github.com/be5invis/Sarasa-Gothic)**，并把它加到 `--font-mono` 字体栈里。

## 兼容性

- **已测试平台**：Windows 10/11 上的 Typora 1.13.4。
- **未测试平台**：macOS、Linux。理论上能用（Typora 是 Electron，CSS 跨平台），但作者没有验证过。出问题欢迎提 issue。
- **GFM 警告块** (`> [!NOTE]` 等) 需要 Typora 1.7+ — 较老版本会渲染成普通引用块。
- **Mermaid 图表** 针对 Typora 当前的 SVG 渲染器优化；老版 Typora 渲染可能会有微小差异。
- 主题使用了 CSS `:has()` 选择器，需要较新的 Chromium 内核（Typora ≥ ~1.5 自带）。

## 致谢

- **代码配色** — Atom 编辑器的 One Dark 主题
- **字体** — 霞骛文楷由 [lxgw](https://github.com/lxgw) 维护，JetBrains Mono 由 JetBrains 设计
- **GitHub 警告 class** — Typora 1.13+ 原生的 `md-alert` 渲染

## 许可

MIT — 欢迎 fork、修改、分享。
