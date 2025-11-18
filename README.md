# LaTeX Beamer 简约模板

一个支持中英双语的简约 beamer 演示文稿模板，包含自定义主题（母版）和常用页面类型。

## 功能特性

- ✅ **中英双语支持**：英文默认 Arial，中文默认宋体（SimSun）
- ✅ **首页（封面）**：自动生成标题页
- ✅ **总目录页**：完整的演示文稿目录
- ✅ **分节页**：每个 section 自动插入分节标题页和当前章节目录
- ✅ **致谢页**：使用 `\thanksframe` 命令
- ✅ **统一页脚**：显示作者和页码（页码/总页数）

## 编译要求

- **编译引擎**：必须使用 **XeLaTeX**（因为使用了 `fontspec` 和 `xeCJK`）
- **TeX 发行版**：TeX Live、MiKTeX 等均可

## 快速开始

### 1. 编译

```bash
xelatex main.tex
```

或者使用 Overleaf：
- 上传 `main.tex` 和 `mybasic.sty`
- 在 Overleaf 中设置编译器为 **XeLaTeX**

### 2. 修改内容

编辑 `main.tex`：

```latex
\title{你的标题 / Your Title}
\subtitle{副标题 / Subtitle}
\author[短名]{完整名字 / Full Name}
\institute{你的单位 / Your Organization}
\date{\today}
```

### 3. 添加内容

在 `\begin{document}` 和 `\end{document}` 之间：

- **添加 section**：使用 `\section{章节名}`
- **添加幻灯片**：使用 `\begin{frame}{标题}...\end{frame}`
- **添加致谢页**：使用 `\thanksframe[自定义文字]`

## 页面结构说明

### 首页（封面）
```latex
\begin{frame}[plain]
  \titlepage
\end{frame}
```

### 总目录页
```latex
\begin{frame}{Outline / 总目录}
  \tableofcontents
\end{frame}
```

### 分节页（自动生成）
当使用 `\section{章节名}` 时，会自动：
1. 插入一个分节标题页（显示章节名）
2. 插入一个当前章节的目录页（可选，可通过 `\DisableSectionTOC` 禁用）

### 致谢页
```latex
\thanksframe[Thank You / 谢谢]
```

## 自定义选项

### 禁用分节目录
如果不想在每个 section 开头显示目录页：

```latex
\DisableSectionTOC  % 在 \begin{document} 之前添加
```

### 重新启用分节目录
```latex
\EnableSectionTOC  % 在 \begin{document} 之前添加
```

## 文件说明

- `main.tex`：主文件，包含演示文稿内容
- `mybasic.sty`：自定义主题文件（母版），包含：
  - 字体设置（Arial + SimSun）
  - 颜色主题（蓝色基调）
  - 页脚模板
  - 标题页模板
  - 分节页模板
  - 致谢页命令

## 颜色主题

- **Primary（主色）**：RGB(0,86,179) - 用于标题和强调
- **Accent（辅助色）**：RGB(242,101,34) - 用于局部强调
- **LightText（浅色文字）**：RGB(90,90,90) - 用于副标题和页脚

如需修改颜色，编辑 `mybasic.sty` 中的颜色定义。

## 常见问题

### Q: 编译报错 "fontspec" 或 "xeCJK" 找不到
**A:** 确保使用 XeLaTeX 编译，而不是 pdfLaTeX。

### Q: 中文字体显示不正确
**A:** 确保系统已安装 SimSun（宋体）字体。Windows 系统通常自带，Linux/Mac 可能需要安装。

### Q: 如何修改字体？
**A:** 编辑 `mybasic.sty` 中的字体设置：
```latex
\setsansfont{Arial}           % 英文字体
\setCJKmainfont{SimSun}       % 中文字体
```

## 示例输出

模板包含以下示例内容：
- Section 1: Introduction / 引言
- Section 2: Design / 设计
- Section 3: Thanks / 致谢

可以直接编译查看效果，然后替换为自己的内容。

## 许可证（License）

本模板采用 **MIT License** 授权，你可以自由使用、修改和分发本项目，包括个人和商业用途，但需要在再分发时保留原始版权和许可证声明。

```text
MIT License

Copyright (c) 2025 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

