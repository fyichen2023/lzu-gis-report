# 更新日志

本文档记录了项目的所有重要变更。

格式基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.0.0/)，
版本号遵循 [语义化版本](https://semver.org/lang/zh-CN/)。

## [未发布]

### 计划中
- 添加更多代码高亮语言支持
- 改进 PDF 书签和目录生成
- 添加更多实习报告完整示例
- 支持 Overleaf 在线编辑

## [1.0.0] - 2026-01-12

### 新增
- 初始版本发布
- 创建 `lzu-gis-report.cls` 文档类
- 实现 `ReportBox` 核心环境，完美模拟 Word 表格样式
- 内置 Python 代码高亮样式
- 提供完整的示例文档 `example.tex`
- 编写详细的 README.md 和 QUICKSTART.md
- 添加 CONTRIBUTING.md 贡献指南
- 采用 MIT 开源许可证
- 配置 .gitignore 忽略 LaTeX 编译产物

### 特性
- 支持跨页显示，内容不会溢出
- 自动边框对齐，相邻盒子无缝连接
- 简洁的命令接口：`\labNumber`, `\labTitle`, `\studentName`, `\studentID`
- 一键生成报告头部：`\makeReportHeader`
- 完善的中文支持（基于 ctex）
- 数学公式完美排版
- 图表标题自动编号

### 文档
- README.md：项目介绍和快速开始
- QUICKSTART.md：详细的使用指南
- CONTRIBUTING.md：贡献者指南
- LICENSE：MIT 许可证
- example.tex：完整的使用示例

---

## 版本说明

### 语义化版本

- **主版本号（MAJOR）**：不兼容的 API 修改
- **次版本号（MINOR）**：向下兼容的功能性新增
- **修订号（PATCH）**：向下兼容的问题修正

### 变更类型

- `新增`：新功能
- `变更`：对现有功能的变更
- `弃用`：即将移除的功能
- `移除`：已移除的功能
- `修复`：Bug 修复
- `安全`：安全性修复

---

[未发布]: https://github.com/fyichen2023/lzu-gis-report-template/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/fyichen2023/lzu-gis-report-template/releases/tag/v1.0.0
