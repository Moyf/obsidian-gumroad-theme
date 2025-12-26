# 🚀 GitHub Actions 发布工作流

这个目录包含了用于自动发布 Brutal Gum 主题的 GitHub Actions 工作流。

## 📁 文件说明

### 1. `auto-release.yml` - 自动发布
**触发条件**: 当 `manifest.json` 或 `theme.css` 文件被推送到 `main`/`master` 分支时自动触发。

**工作流程**:
1. 检测版本号变更
2. 生成发布说明
3. 创建 Git 标签
4. 发布 GitHub Release
5. 上传主题文件

**使用方法**:
```bash
# 1. 修改版本号
# 编辑 manifest.json，将 version 改为新版本号

# 2. 提交更改
git add manifest.json theme.css
git commit -m "release: v0.1.6"

# 3. 推送
git push origin main

# 4. 等待 GitHub Actions 自动完成
# 可在 GitHub 仓库的 Actions 标签页查看进度
```

---

### 2. `manual-release.yml` - 手动发布
**触发方式**: 在 GitHub Actions 页面手动运行工作流。

**工作流程**:
1. 验证版本号格式
2. 更新 `manifest.json`
3. 生成发布说明
4. 创建 Git 标签
5. 发布 GitHub Release
6. 上传所有相关文件

**使用方法**:
1. 访问 GitHub 仓库 → **Actions** 标签页
2. 选择 **Manual Release** 工作流
3. 点击 **Run workflow** 按钮
4. 填写参数：
   - **Version**: 版本号（必填，如：`0.1.7`）
   - **Release notes**: 自定义发布说明（可选）
   - **Is prerelease**: 是否为预发布版本（可选，默认为 `false`）
5. 点击 **Run workflow** 执行

**手动发布的优势**:
- ✅ 可以自定义版本号，无需修改文件
- ✅ 可以添加详细的发布说明
- ✅ 可以标记为预发布版本
- ✅ 适合紧急修复或特殊发布

---

## 🎯 两种发布方式对比

| 特性 | 自动发布 | 手动发布 |
|------|---------|---------|
| **触发方式** | 推送代码 | 手动点击 |
| **版本号** | 从 manifest.json 读取 | 手动输入 |
| **发布说明** | 自动生成（基于提交历史） | 可自定义 |
| **预发布** | 不支持 | 支持 |
| **适用场景** | 日常开发 | 紧急修复/特殊版本 |

---

## 🔧 配置说明

### 必需的 Secret
工作流使用 GitHub 自动提供的 `GITHUB_TOKEN`，无需额外配置。

### 可选的环境变量
如果需要自定义，可以在仓库的 **Settings** → **Secrets and variables** → **Actions** 中添加：

- `THEME_NAME`: 主题名称（默认从 manifest.json 读取）

---

## 📦 发布内容

每次发布包含以下文件：

1. **theme.css** - 主题样式文件（必需）
2. **manifest.json** - 主题配置文件（必需）
3. **package.json** - 开发配置文件（可选）

---

## 📝 发布说明模板

### 自动生成的格式
```markdown
## 🎉 Brutal Gum v0.1.6

### ✨ 本次更新内容

- 优化深色模式配色
- 修复 Callout 显示问题
- 新增按钮交互效果

### 📦 包含文件

- `theme.css` - 主题样式文件
- `manifest.json` - 主题配置

### 🔗 快速使用

1. 下载 `theme.css`
2. 在 Obsidian 设置 → 外观 → 主题 → 管理 → 手动安装主题
3. 选择并应用主题

---

*发布于 2025-12-27 14:30:00*
```

### 自定义发布说明
在手动发布时，可以填写自定义说明，例如：
```
紧急修复：解决了在 iOS 设备上主题不生效的问题。
同时优化了代码块的显示效果。
```

---

## ⚠️ 注意事项

1. **版本号格式**: 必须遵循语义化版本规范（如：`0.1.6`）
2. **Git 标签**: 如果标签已存在，会自动覆盖
3. **发布失败**: 检查 GitHub Actions 日志，常见问题：
   - 版本号格式错误
   - 文件路径错误
   - 权限不足

---

## 🔍 故障排查

### 问题：自动发布未触发
**解决方案**:
- 检查是否修改了 `manifest.json` 或 `theme.css`
- 确认推送到正确的分支（main/master）
- 查看 Actions 是否被禁用

### 问题：版本号未更新
**解决方案**:
- 确保 `manifest.json` 中的版本号确实变更
- 检查 Git 提交历史

### 问题：手动发布失败
**解决方案**:
- 检查版本号格式是否正确
- 查看 Actions 日志中的具体错误信息

---

## 📚 参考资料

- [GitHub Actions 官方文档](https://docs.github.com/actions)
- [Obsidian 主题发布指南](https://docs.obsidian.md/Themes/App+themes/Theme+guidelines)
- [语义化版本 2.0.0](https://semver.org/lang/zh-CN/)

---

## 💡 最佳实践

1. **日常开发**: 使用自动发布
   - 保持提交信息清晰
   - 及时更新版本号

2. **紧急修复**: 使用手动发布
   - 快速发布修复
   - 添加详细说明

3. **版本管理**:
   - 小改动：修订号 +1（0.1.5 → 0.1.6）
   - 新功能：次版本号 +1（0.1.6 → 0.2.0）
   - 重大变更：主版本号 +1（0.1.6 → 1.0.0）

4. **发布说明**:
   - 简洁明了
   - 突出重点变更
   - 提供使用指引
