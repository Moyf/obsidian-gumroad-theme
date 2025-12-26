# 📝 Changelog - Brutal Gum Theme

所有重大变更都会记录在此文件中。

---

## [Unreleased]

### Added
-

### Changed
-

### Fixed
-

---

## [0.1.6] - 2025-12-27

### Changed
- **深色模式优化**: 重新设计配色方案，提升对比度和可读性
- **标题颜色**: H1 标题现在支持 `--color-accent` 变量，提高主题自定义性
- **按钮交互**: 新增点击状态效果，提供触觉反馈
- **社区项目卡片**: 新增悬停和选中状态样式
- **Callout 大幅改进**:
  - 统一所有 Callout 的 padding 和间距
  - 重新设计颜色方案（蓝/黄/红/紫）
  - 优化编辑按钮位置，支持动态移动
- **引用块**: 调整引用符号位置，修复字体对齐问题
- **图片样式**: 添加过渡动画，Callout 内图片保持简洁
- **UI 控件**: 移除按钮粗体，保持简洁风格
- **嵌入块**: 修复深色模式下编辑按钮颜色

### Fixed
- 内联代码格式化问题
- Callout 内图片显示问题
- 外部链接 URL 格式化显示

### Added
- **插件兼容性增强**:
  - Export Image 边框颜色调整
  - Notebook Navigator 文件标签背景修复
  - Note Toolbar 工具栏 Callout 样式优化
  - Ember 勋章样式适配
- 隐藏外部链接的 URL 格式化文本

---

## [0.1.5] - 2025-12-26

### Changed
- 优化边框和阴影细节
- 精炼 UI 元素的边框样式

### Fixed
- 边框修复
- 滚动条隐藏功能

---

## [0.1.4] - 2025-12-25

### Added
- 初始版本发布
- Brutalist 风格设计
- 深色/浅色模式支持
- 基础组件样式

---

## 📝 版本号说明

本项目遵循 [语义化版本](https://semver.org/lang/zh-CN/)：

- **主版本号 (Major)**: 不兼容的重大变更
- **次版本号 (Minor)**: 向后兼容的功能新增
- **修订号 (Patch)**: 向后兼容的问题修正

---

## 🚀 如何使用

### 自动发布（推荐）

1. 修改 `manifest.json` 中的版本号
2. 提交并推送到 `main` 分支
3. GitHub Actions 会自动：
   - 检测版本变更
   - 创建 Git 标签
   - 生成 Release Notes
   - 发布 GitHub Release
   - 上传主题文件

### 手动发布

1. 在 GitHub 仓库的 **Actions** 标签页
2. 选择 **Manual Release** 工作流
3. 点击 **Run workflow**
4. 输入版本号（如：0.1.7）
5. 可选：输入自定义发布说明
6. 点击 **Run workflow** 执行

---

## 🔧 开发工作流

```bash
# 1. 开发时使用 SCSS（如果有）
npm run watch

# 2. 构建 CSS
npm run build

# 3. 修改 manifest.json 版本号
# 4. 提交更改
git add .
git commit -m "feat: 新功能描述"

# 5. 推送到主分支触发自动发布
git push origin main
```

---

## 📦 发布内容

每次发布包含：

- `theme.css` - 主题样式文件
- `manifest.json` - 主题配置文件
- `CHANGELOG.md` - 更新日志（可选）

---

## 🔗 相关链接

- [Obsidian 主题文档](https://docs.obsidian.md/Themes/App+themes/Theme+guidelines)
- [语义化版本规范](https://semver.org/lang/zh-CN/)
- [GitHub Actions 文档](https://docs.github.com/actions)
