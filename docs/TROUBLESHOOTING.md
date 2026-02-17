# 故障排除指南

## 自动补全出现异常

请按顺序尝试以下步骤：

### 第一步：重置项目缓存

1. 在工作区按下 `Ctrl + Shift + P`
2. 搜索 `Spyglass: Reset Project Cache` 并执行
3. 等待项目缓存重置完成
4. 重启 VSCode

### 第二步：检查安装

如果上述操作不存在或无效：

- 检查 `Spyglass` 插件是否正确安装（标识符spgoding.datapack-language-server）
- 确认 `spyglass.json` 文件配置正确
- 验证文件路径是否为纯英文，有时候存在中文的路径会无法工作
- 验证文件路径是否存在空格，有时候存在空格的路径会无法工作

### 第三步：尝试降级

- 在vscode插件界面搜索spyglass（或搜索标识符spgoding.datapack-language-server）
- 取消勾选插件的 自动更新 选项
- 卸载spyglass后重启vscode
- 再次搜索spyglass插件，并点击安装按钮边上的小箭头选择安装指定版本
- 于2026年春节期间测试已知 4.6.1 版本的spyglass可正常工作

---

仍然有问题？报告错误
