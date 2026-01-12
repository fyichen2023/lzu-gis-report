# LZU GIS 实习报告 LaTeX 模板

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![LaTeX](https://img.shields.io/badge/LaTeX-Template-blue.svg)](https://www.latex-project.org/)

> 一个现代化的 LaTeX 模板，专为兰州大学 GIS 空间分析课程实习报告设计

## 项目背景

作为兰州大学地理信息专业的学生，某学期需要完成多次 GIS 空间分析实习报告。然而，提供的传统 Word 表格模板存在一些不可忽视的使用体验问题：

- **格式易碎**：表格在内容调整时容易发生错位和变形
- **维护困难**：多个盒子之间的边框对齐需要手动调整，耗时且容易出错
- **版本管理不便**：Word 的二进制格式不利于使用 Git 等版本控制工具
- **排版受限**：对于复杂的数学公式和代码块，Word 的展示效果不够理想
- **跨平台兼容性**：不同版本的 Word 可能出现格式不一致的情况

## 项目目标

本项目旨在通过 LaTeX 技术实现原有 Word 模板格式的**像素级复刻与现代化重构**，提供：

- **视觉一致性**：完全模拟原有 Word 表格的外观效果
- **高度可维护**：使用简洁的 LaTeX 命令，内容与格式分离
- **开箱即用**：封装为 `.cls` 文档类，用户只需专注于内容编写
- **功能增强**：
  - 支持跨页显示，不再担心内容溢出
  - 内置代码高亮样式（支持 Python、R、SQL 等）
  - 完善的数学公式支持
  - 自动生成目录和交叉引用
  - 适配 Git 版本控制

## 主要特性

### 核心环境：ReportBox

模板提供了 `ReportBox` 环境，完美复刻 Word 表格样式：

```latex
\begin{ReportBox}{实习目的}
    本次实习的目的是……
\end{ReportBox}
```

**特点**：
- 直角边框，模拟 Word 表格视觉效果
- 支持自动跨页，长内容不会溢出
- 边框无缝连接，相邻盒子边框自动重叠
- 标题与内容格式化，无需手动调整

### 代码高亮

内置 `listings` 包配置，支持多种编程语言：

```latex
\begin{lstlisting}[language=Python]
import arcpy
arcpy.Buffer_analysis("input", "output", "500 Meters")
\end{lstlisting}
```

### 数学公式

完美支持 LaTeX 数学公式排版：

```latex
\begin{equation}
    V = V_m \times \frac{S^b A^c}{(S^b A^c)_m}
\end{equation}
```

## 安装与使用

### 环境要求

- **TeX 发行版**：TeX Live（推荐）或 MiKTeX
- **编译引擎**：XeLaTeX 或 LuaLaTeX（必需，以支持中文）
- **必需宏包**：ctex, tcolorbox, listings, geometry, graphicx 等（通常已包含在完整安装中）

### 快速开始

1. **克隆仓库**

   ```bash
   git clone https://github.com/fyichen2023/lzu-gis-report-template.git
   cd lzu-gis-report-template
   ```

2. **查看示例**

   打开 `example.tex` 查看完整的使用示例。

3. **编译文档**

   使用 XeLaTeX 编译（推荐）：

   ```bash
   xelatex example.tex
   xelatex example.tex  # 再次编译以生成完整的交叉引用
   ```

   或在你喜欢的 LaTeX 编辑器（如 TeXworks, TeXstudio, VS Code 等）中打开并编译。

4. **开始创作**

   复制 `example.tex` 并重命名，修改文档信息：

   ```latex
   \documentclass{lzu-gis-report}
   
   \labNumber{13}
   \labTitle{水系提取与洪水流量过程预测}
   \studentName{你的姓名}
   \studentID{你的学号}
   
   \begin{document}
   \makeReportHeader
   
   \begin{ReportBox}{背景}
       你的内容...
   \end{ReportBox}
   
   % 更多内容...
   
   \end{document}
   ```

## 文档结构

```
lzu-gis-report-template/
├── lzu-gis-report.cls    # 模板文档类文件
├── example.tex           # 完整示例文档
├── 13.tex               # 原始实习报告示例
├── README.md            # 本说明文档
├── LICENSE              # MIT 许可证
├── .gitignore           # Git 忽略文件配置
└── figures/             # 图片资源文件夹（可选）
```

## 自定义配置

### 修改页边距

在 `.cls` 文件中找到以下行并修改：

```latex
\RequirePackage[left=2.5cm,right=2.5cm,top=2.5cm,bottom=2.5cm]{geometry}
```

### 调整盒子边框样式

修改 `ReportBox` 环境的 `boxrule` 参数：

```latex
\newtcolorbox{ReportBox}[1]{
    ...
    boxrule=0.5pt,  % 修改此处调整边框粗细
    ...
}
```

### 添加新的代码样式

在 `.cls` 文件中仿照 `pythonstyle` 定义新样式：

```latex
\lstdefinestyle{sqlstyle}{
    language=SQL,
    basicstyle=\ttfamily\footnotesize,
    ...
}
```

## 贡献指南

欢迎贡献！如果你发现 bug 或有改进建议，请：

1. Fork 本仓库
2. 创建你的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的修改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开一个 Pull Request

## 许可证

本项目采用 [MIT 许可证](LICENSE)。你可以自由使用、修改和分发本模板。

## 致谢

- 感谢 LaTeX 社区提供的强大工具和宏包
- 感谢 `tcolorbox` 宏包的作者，提供了灵活的盒子绘制功能
- 感谢所有为本项目提出建议和反馈的同学们

## 联系方式

如有问题或建议，请通过以下方式联系：

- **GitHub**: [fyichen2023](https://github.com/fyichen2023)
- **邮箱**: fyichen2023@lzu.edu.cn

---

**Star ⭐ 本项目以支持更多同学摆脱 Word 表格的困扰！**
