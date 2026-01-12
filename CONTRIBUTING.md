# 贡献指南

感谢你考虑为 LZU GIS 实习报告模板做出贡献！

本文档提供了如何为项目做出贡献的指导。

## 贡献方式

你可以通过以下方式为项目做出贡献：

- **报告 Bug**：发现问题？请提交 Issue
- **提出新功能**：有好的想法？我们很乐意听取
- **改进文档**：发现文档不清楚或有错误？帮助我们改进
- **提交代码**：修复 Bug 或实现新功能
- **分享使用经验**：在 Discussions 中分享你的使用心得

## 报告 Bug

在提交 Bug 报告之前，请：

1. **检查现有 Issues**：你的问题可能已经被报告过了
2. **确认问题可复现**：尝试在干净的环境中重现问题
3. **收集信息**：准备好相关的日志、截图等

### Bug 报告模板

```markdown
## 问题描述
简要描述遇到的问题

## 复现步骤
1. 第一步...
2. 第二步...
3. 第三步...

## 期望行为
描述你期望发生的情况

## 实际行为
描述实际发生的情况

## 环境信息
- 操作系统：Windows 11 / macOS 14 / Ubuntu 22.04
- TeX 发行版：TeX Live 2023 / MiKTeX 23.10
- 编译器：XeLaTeX / LuaLaTeX

## 附加信息
- 日志文件（.log）
- 截图
- 最小可复现示例（MWE）
```

## 功能建议

我们欢迎新功能建议！提交时请：

1. **描述清楚**：说明功能的用途和使用场景
2. **解释原因**：为什么需要这个功能？
3. **提供示例**：如果可能，提供使用示例或模拟效果

## 提交代码

### 开发流程

1. **Fork 仓库**

   点击 GitHub 页面右上角的 "Fork" 按钮

2. **克隆你的 Fork**

   ```bash
   git clone https://github.com/fyichen2023/lzu-gis-report-template.git
   cd lzu-gis-report-template
   ```

3. **创建分支**

   ```bash
   git checkout -b feature/your-feature-name
   ```

   分支命名建议：
   - `feature/` - 新功能
   - `fix/` - Bug 修复
   - `docs/` - 文档更新
   - `style/` - 代码格式调整

4. **进行修改**

   按照下面的"代码规范"进行修改

5. **测试你的修改**

   ```bash
   xelatex example.tex
   xelatex example.tex
   ```

   确保：
   - 编译无错误
   - 生成的 PDF 格式正确
   - 新功能按预期工作

6. **提交修改**

   ```bash
   git add .
   git commit -m "feat: 添加新功能的简短描述"
   ```

   Commit 消息规范：
   - `feat:` - 新功能
   - `fix:` - Bug 修复
   - `docs:` - 文档更新
   - `style:` - 格式调整（不影响代码逻辑）
   - `refactor:` - 重构
   - `test:` - 测试相关
   - `chore:` - 构建/工具相关

7. **推送到你的 Fork**

   ```bash
   git push origin feature/your-feature-name
   ```

8. **创建 Pull Request**

   在 GitHub 上打开你的 Fork，点击 "Compare & pull request"

### Pull Request 模板

```markdown
## 变更说明
简要说明本次 PR 的内容

## 变更类型
- [ ] Bug 修复
- [ ] 新功能
- [ ] 文档更新
- [ ] 代码重构
- [ ] 其他（请说明）

## 测试
- [ ] 已在本地测试
- [ ] 编译无错误
- [ ] 生成的 PDF 格式正确

## 截图（如适用）
添加相关截图

## 相关 Issue
关闭 #issue_number
```

## 代码规范

### LaTeX 代码风格

1. **缩进**：使用 4 个空格缩进
2. **注释**：使用 `%` 添加注释，解释复杂的宏定义
3. **命名**：
   - 环境名使用 PascalCase：`ReportBox`
   - 命令名使用 camelCase：`\makeReportHeader`
   - 内部变量使用 `@` 前缀：`\@labNumber`

示例：

```latex
% 定义报告盒子环境
% 参数 #1: 标题文本
\newtcolorbox{ReportBox}[1]{
    enhanced,
    breakable,
    title={#1},
    % 更多选项...
}
```

### 文档规范

1. **Markdown 格式**：
   - 标题使用 ATX 风格（`#`）
   - 代码块指定语言
   - 列表使用 `-` 而非 `*`

2. **中英文混排**：
   - 中英文之间加空格
   - 中文标点使用全角
   - 英文、数字使用半角

3. **示例代码**：
   - 提供完整可运行的示例
   - 添加必要的注释

## 代码审查流程

提交 PR 后，维护者会进行审查：

1. **自动检查**：
   - 编译测试
   - 格式检查

2. **人工审查**：
   - 代码质量
   - 功能实现
   - 文档完整性

3. **反馈**：
   - 审查者会留下评论和建议
   - 请及时回复并进行修改

4. **合并**：
   - 审查通过后，维护者会合并你的 PR
   - 你的贡献将出现在 Contributors 列表中！

## 优先任务

以下是我们目前最需要帮助的方向：

- [ ] 添加更多代码高亮语言支持（R, MATLAB, etc.）
- [ ] 改进 PDF 书签和超链接
- [ ] 添加更多实习报告示例
- [ ] 编写视频教程
- [ ] 支持 Overleaf 在线编辑
- [ ] 性能优化（加快编译速度）

如果你对某个任务感兴趣，欢迎在 Issue 中留言！

## 许可证

贡献的代码将采用与项目相同的 [MIT 许可证](LICENSE)。

提交 PR 即表示你同意：
- 你拥有提交内容的版权
- 你授予项目使用你的贡献的权利
- 你的贡献将在 MIT 许可证下发布

## 致谢

每一个贡献，无论大小，都对项目至关重要。感谢你的支持！

你的名字将出现在：
- Contributors 列表中
- Release Notes 中（如果贡献重要）

## 联系方式

有任何疑问？可以通过以下方式联系：

- **GitHub**: [fyichen2023](https://github.com/fyichen2023)
- **邮箱**: fyichen2023@lzu.edu.cn

---

再次感谢你的贡献！
