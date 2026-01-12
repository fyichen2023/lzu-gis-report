# 快速开始指南

本文档将帮助你快速上手使用 LZU GIS 实习报告模板。

## 🚀 5分钟快速入门

### 步骤 1：准备环境

确保你已经安装了 LaTeX 发行版：

- **Windows**: [TeX Live](https://www.tug.org/texlive/) 或 [MiKTeX](https://miktex.org/)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: 通过包管理器安装 TeX Live

```bash
# Ubuntu/Debian
sudo apt-get install texlive-full

# Fedora
sudo dnf install texlive-scheme-full

# Arch Linux
sudo pacman -S texlive-most
```

### 步骤 2：下载模板

```bash
git clone https://github.com/yourusername/lzu-gis-report-template.git
cd lzu-gis-report-template
```

或者直接下载 ZIP 文件并解压。

### 步骤 3：编译示例文档

使用命令行：

```bash
xelatex example.tex
xelatex example.tex  # 再次编译以生成完整的交叉引用
```

或者使用你喜欢的 LaTeX 编辑器：

- **TeXstudio**: 打开 `example.tex`，按 F5 或点击"构建并查看"
- **VS Code**: 安装 LaTeX Workshop 插件，打开 `example.tex`，按 Ctrl+Alt+B
- **Overleaf**: 上传所有文件到 Overleaf，设置编译器为 XeLaTeX

### 步骤 4：创建你的报告

1. 复制 `example.tex` 并重命名：

   ```bash
   cp example.tex my-lab-report.tex
   ```

2. 打开 `my-lab-report.tex`，修改文档信息：

   ```latex
   \labNumber{13}
   \labTitle{水系提取与洪水流量过程预测}
   \studentName{你的姓名}
   \studentID{你的学号}
   ```

3. 开始编写内容！

## 📝 基本用法

### 报告头部

每个报告都需要设置基本信息并生成头部：

```latex
\documentclass{lzu-gis-report}

% 设置信息
\labNumber{01}
\labTitle{你的实习题目}
\studentName{张三}
\studentID{320230000000}

\begin{document}

% 生成头部（包含实习序号和实习人信息）
\makeReportHeader

% 后续内容...
\end{document}
```

### ReportBox 环境

所有内容都应放在 `ReportBox` 环境中：

```latex
\begin{ReportBox}{标题}
    你的内容...
\end{ReportBox}
```

常用的盒子标题：
- 背景
- 实习目的
- 实习内容
- 实习数据及数据说明（原始数据的坐标系统及主要属性字段）
- 基本原理
- 应用到的基本工具
- 操作流程图（尽量为图解模型）
- 操作步骤（方法）
- 结果与分析
- 存在问题与解决办法
- 总结与个人体会
- 其他的解决办法（工具名称，解决思路，甚至其他软件名称及相应工具）

### 插入图片

```latex
\begin{ReportBox}{操作流程图}
    \begin{figure}[H]
        \centering
        \includegraphics[width=0.7\textwidth]{figures/workflow.png}
        \caption{工作流程示意图}
        \label{fig:workflow}
    \end{figure}
\end{ReportBox}
```

**注意**：
- 图片文件建议放在 `figures/` 文件夹中
- 支持的格式：PDF（矢量图，推荐）、PNG、JPG
- 使用 `[H]` 参数强制图片位置

### 插入表格

```latex
\begin{ReportBox}{统计结果}
    \begin{table}[H]
        \centering
        \caption{数据统计表}
        \begin{tabular}{|l|r|r|}
        \hline
        \textbf{类别} & \textbf{数量} & \textbf{占比} \\
        \hline
        类别 A & 1234 & 45.6\% \\
        类别 B & 2345 & 54.4\% \\
        \hline
        \end{tabular}
        \label{tab:statistics}
    \end{table}
\end{ReportBox}
```

### 插入代码

```latex
\begin{ReportBox}{Python代码示例}
\begin{lstlisting}[language=Python, caption={缓冲区分析}]
import arcpy

# 设置工作空间
arcpy.env.workspace = r"C:\data.gdb"

# 执行缓冲区分析
arcpy.Buffer_analysis("roads", "roads_buffer", "500 Meters")
\end{lstlisting}
\end{ReportBox}
```

支持的语言：Python, R, SQL, C, C++, Java, JavaScript 等。

### 数学公式

行内公式：

```latex
Maidment速度场公式为 $V = V_m \times \frac{S^b A^c}{(S^b A^c)_m}$
```

独立公式：

```latex
\begin{equation}
    V = V_m \times \frac{S^b A^c}{(S^b A^c)_m}
\end{equation}
```

### 列表

无序列表：

```latex
\begin{itemize}
    \item 第一点
    \item 第二点
    \item 第三点
\end{itemize}
```

有序列表：

```latex
\begin{enumerate}
    \item 第一步
    \item 第二步
    \item 第三步
\end{enumerate}
```

嵌套列表：

```latex
\begin{enumerate}
    \item 主要步骤
    \begin{itemize}
        \item 子步骤 1
        \item 子步骤 2
    \end{itemize}
    \item 下一个主要步骤
\end{enumerate}
```

## 🔧 常见问题

### Q: 编译时提示缺少宏包怎么办？

**A**: 大多数宏包在 TeX Live 完整安装中都已包含。如果遇到缺失：

- **TeX Live**: 宏包会自动下载（需要联网）
- **MiKTeX**: 首次使用时会提示安装，点击"是"即可

手动安装宏包：

```bash
# TeX Live
tlmgr install tcolorbox

# MiKTeX
mpm --install=tcolorbox
```

### Q: 中文显示乱码怎么办？

**A**: 确保使用 **XeLaTeX** 或 **LuaLaTeX** 编译，不要使用 pdfLaTeX。

### Q: 图片无法显示？

**A**: 检查：
1. 图片路径是否正确（相对路径）
2. 图片文件是否存在
3. 图片格式是否支持（PDF, PNG, JPG）

### Q: 如何调整页边距？

**A**: 在 `lzu-gis-report.cls` 文件中修改：

```latex
\RequirePackage[left=2.5cm,right=2.5cm,top=2.5cm,bottom=2.5cm]{geometry}
```

### Q: 如何更改字体大小？

**A**: 文档类选项中修改：

```latex
\documentclass[12pt]{lzu-gis-report}  % 12pt（默认）、10pt、11pt
```

或在特定位置使用：

```latex
{\small 较小的文字}
{\large 较大的文字}
{\Large 更大的文字}
```

## 💡 进阶技巧

### 自定义盒子样式

如果需要特殊样式的盒子，可以在文档中定义新环境：

```latex
\newtcolorbox{WarningBox}[1]{
    enhanced,
    breakable,
    colback=yellow!10,
    colframe=red!75!black,
    title={⚠️ #1}
}

\begin{WarningBox}{注意事项}
    这是一个警告盒子
\end{WarningBox}
```

### 使用 BibTeX 管理参考文献

1. 创建 `references.bib` 文件
2. 在文档末尾添加：

```latex
\bibliographystyle{plain}
\bibliography{references}
```

3. 编译顺序：

```bash
xelatex document.tex
bibtex document
xelatex document.tex
xelatex document.tex
```

### 使用 Git 版本控制

```bash
git init
git add .
git commit -m "Initial commit"
```

## 📚 更多资源

- [LaTeX 官方文档](https://www.latex-project.org/help/documentation/)
- [CTAN 宏包搜索](https://www.ctan.org/)
- [TeX Stack Exchange](https://tex.stackexchange.com/)
- [一份不太简短的 LaTeX 介绍](http://mirrors.ctan.org/info/lshort/chinese/lshort-zh-cn.pdf)

## 🆘 获取帮助

如果遇到问题，可以：

1. 查看本文档的"常见问题"部分
2. 查看 [GitHub Issues](https://github.com/yourusername/lzu-gis-report-template/issues)
3. 提交新的 Issue

---

祝你使用愉快！如有建议，欢迎反馈。
