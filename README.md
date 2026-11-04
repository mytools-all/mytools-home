# MyTools 项目索引

Windows 插件工具箱，Tauri 2 + Vue 3 + Rust。宿主和每个插件使用独立 Git 仓库；项目代码使用 MIT，第三方代码保留自身许可。宿主和其他工具当前版本为 0.1.0，合并 Demo 为 0.1.1（待重新发布）。

## 宿主

[mytools](https://github.com/mytools-all/mytools)：应用平台、启动器、插件管理、我的面板、权限与宿主能力。克隆到本地 app 目录后按该仓库 README 构建。

## 插件

11 个工具插件可从 npm 安装；mytools-demo 的合并源码已完成，其 npm 包已被撤回，等待重新发布。索引中的 `published: true` 表示已经核验可用。

插件 npm 作用域为 `@mytools-all`；[database.json](plugins/database.json) 维护包名与版本索引。各插件可独立开发、测试和发布。

| 插件仓库 | npm 包 |
|---|---|
| [mytools-demo](https://github.com/mytools-all/mytools-demo) | [@mytools-all/mytools-demo](https://www.npmjs.com/package/@mytools-all/mytools-demo) |
| [mytools-calc](https://github.com/mytools-all/mytools-calc) | [@mytools-all/mytools-calc](https://www.npmjs.com/package/@mytools-all/mytools-calc) |
| [mytools-clipboard](https://github.com/mytools-all/mytools-clipboard) | [@mytools-all/mytools-clipboard](https://www.npmjs.com/package/@mytools-all/mytools-clipboard) |
| [mytools-color](https://github.com/mytools-all/mytools-color) | [@mytools-all/mytools-color](https://www.npmjs.com/package/@mytools-all/mytools-color) |
| [mytools-color-picker](https://github.com/mytools-all/mytools-color-picker) | [@mytools-all/mytools-color-picker](https://www.npmjs.com/package/@mytools-all/mytools-color-picker) |
| [mytools-ctool](https://github.com/mytools-all/mytools-ctool) | [@mytools-all/mytools-ctool](https://www.npmjs.com/package/@mytools-all/mytools-ctool) |
| [mytools-ipconfig](https://github.com/mytools-all/mytools-ipconfig) | [@mytools-all/mytools-ipconfig](https://www.npmjs.com/package/@mytools-all/mytools-ipconfig) |
| [mytools-json](https://github.com/mytools-all/mytools-json) | [@mytools-all/mytools-json](https://www.npmjs.com/package/@mytools-all/mytools-json) |
| [mytools-markdown](https://github.com/mytools-all/mytools-markdown) | [@mytools-all/mytools-markdown](https://www.npmjs.com/package/@mytools-all/mytools-markdown) |
| [mytools-ocr](https://github.com/mytools-all/mytools-ocr) | [@mytools-all/mytools-ocr](https://www.npmjs.com/package/@mytools-all/mytools-ocr) |
| [mytools-rename](https://github.com/mytools-all/mytools-rename) | [@mytools-all/mytools-rename](https://www.npmjs.com/package/@mytools-all/mytools-rename) |
| [mytools-search](https://github.com/mytools-all/mytools-search) | [@mytools-all/mytools-search](https://www.npmjs.com/package/@mytools-all/mytools-search) |

## 发布进度

宿主、索引和全部 12 个插件仓库已推送到 GitHub。11 个工具 npm 包可安装，统一 Demo 目前通过合并源码目录安装，重新发布完成后更新索引。

## 本地布局

```text
mytools-home/
├── README.md
├── app/                    # mytools 独立仓库
└── plugins/
    ├── database.json       # 本仓库管理
    └── <插件名>/           # 每个插件独立仓库
```

根仓库只跟踪索引和介绍；app 和插件目录不作为子模块提交。克隆本仓库不会自动下载它们，请根据上面的链接分别克隆。插件商店进入时读取本仓库的 plugins/database.json，更新失败时使用已验证缓存或随应用提供的离线快照。分类、简介、作者、版本、关键词和使用说明均以此 JSON 为商店维护入口；npm 负责实际包分发。

## 索引维护

只编辑 `plugins/database.json` 并推送。本软件会异步刷新商店目录，字段会在前端严格校验。当前格式为 schemaVersion 2，每项包含插件身份 name、npm 包名、版本、published、title、description、category、author、license、repository、features、keywords、notes 和 capabilities；icon、homepage、reference、replaces 可选。参考链接只用于说明交互来源。

安装始终使用宿主当前统一插件根目录，不为单个插件选择位置。目录中的能力描述用于展示，运行权限仍以安装包清单与宿主校验为准。

`demo-hello` 已更名为 `mytools-demo`；旧 GitHub 地址重定向，新 npm 包为 `@mytools-all/mytools-demo`，旧 demo-hello npm 包已撤回。

示例源码统一维护在 mytools-demo，已合并 mytools-hello 的两个读取操作。mytools-demo 的旧 npm 包已由维护者撤回，合并源码可通过本地目录安装；相同包版本不能重复发布，合并版已确定为 0.1.1，重新发布需等待 npm 撤包冷却期结束。

清理状态：mytools-hello 的 GitHub 仓库及 npm 包、demo-hello 的 npm 包均已移除；GitHub 的 demo-hello 旧链接仅重定向至保留的 mytools-demo 仓库。

## 跨工具交接与插件开发

任何 AI 工具或维护者先读 [AGENTS.md](AGENTS.md)。克隆宿主后使用 [项目上下文](https://github.com/mytools-all/mytools/blob/main/docs/PROJECT-CONTEXT.md)、[插件开发指南](https://github.com/mytools-all/mytools/blob/main/docs/plugin-development/README.md) 和 [Demo 案例](https://github.com/mytools-all/mytools/blob/main/docs/plugin-development/demo-walkthrough.md)，不依赖历史聊天。

本地新增“我的日历”验证插件位于 plugins/mytools-calendar，版本 0.1.0；支持公农历/节日、闰月跳转和每日标签待办。源码仓库为 [mytools-calendar](https://github.com/mytools-all/mytools-calendar)，未发布 npm，索引 published:false。详见宿主 docs/plugin-development/validation-calendar.md。
