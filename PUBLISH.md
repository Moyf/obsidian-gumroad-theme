# 🚀 快速发布指南

## ⚡ 最快的发布方式（自动）

修改版本号 → 提交 → 推送 → 完成！

```bash
# 1. 修改 manifest.json 中的 version
# 2. 提交并推送
git add manifest.json theme.css
git commit -m "release: v0.1.6"
git push origin main

# 3. 等待 1-2 分钟，GitHub Actions 会自动发布
```

---

## 🎯 手动发布（自定义）

1. 访问 GitHub → Actions → Manual Release
2. 点击 "Run workflow"
3. 填写版本号（如：0.1.7）
4. 可选：填写发布说明
5. 点击运行

---

## 📋 发布清单

- [ ] 版本号已更新（manifest.json）
- [ ] 主题文件已修改完成（theme.css）
- [ ] 更新日志已记录（CHANGELOG.md）
- [ ] 测试主题效果
- [ ] 提交代码
- [ ] 推送到主分支

---

## 🔗 快速链接

- 📝 [完整工作流文档](.github/workflows/README.md)
- 📝 [更新日志](CHANGELOG.md)
- ⚙️ [自动发布配置](.github/workflows/auto-release.yml)
- ⚙️ [手动发布配置](.github/workflows/manual-release.yml)

---

## 💡 提示

**自动发布**适合日常开发，**手动发布**适合紧急修复。

两种方式都会：
- ✅ 创建 Git 标签
- ✅ 发布 GitHub Release
- ✅ 上传主题文件
- ✅ 生成发布说明
