# MyTools 工作区交接入口

本文件供任何 AI 编程工具或人工维护者阅读，不依赖特定聊天记录、模型、编辑器或插件。

## 先读什么

1. `README.md`：仓库布局与项目链接。
2. `app/docs/PROJECT-CONTEXT.md`：实际架构、运行、数据、边界与已知限制。
3. 修改宿主前读 `app/AGENTS.md`；开发插件读 `app/docs/plugin-development/README.md`。
4. 可运行示例是 `plugins/mytools-demo`；完整业务验证是 `plugins/mytools-calendar`。

## 工作约定

- 根目录是 mytools-home 索引仓库；app 和每个插件都是独立仓库。先检查对应目录的 git status，保留未提交工作。
- 插件独立交付，不引用 app 源码、不直调 Tauri、不因一个插件新增宿主特例。
- 中文界面，项目 MIT，保留第三方许可证。不新增无必要的代码注释。
- 不提交凭据、用户数据、node_modules、target、.npmrc、.env、调试备份。
- 本地修改和安装不代表已经发布。未经当前任务授权，不推送 GitHub、不发布 npm。
- 未发布插件在索引标记 published:false；已核验 mytools-demo 0.1.1 和 mytools-calendar 0.1.0 于 2026-11-04 发布，后续升级仍需明确授权。
- 完成时说明实际检查结果与未验证事项，不把模拟测试当作原生验收。

## 可直接交给其他 AI 的任务开头

“先阅读 AGENTS.md、app/docs/PROJECT-CONTEXT.md 和目标目录的说明，检查 Git 状态。只改本次目标，完成相关测试并报告结果。插件通过公开 API 开发；规范缺项先补文档，再实现，不根据聊天历史猜接口。”
