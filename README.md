# MyTools 项目索引

Windows 插件工具箱，Tauri 2 + Vue 3 + Rust。宿主和每个插件使用独立 Git 仓库；项目代码使用 MIT，第三方代码保留自身许可。当前统一版本 0.1.0。

## 宿主

[mytools](https://github.com/mytools-all/mytools)：应用平台、启动器、插件管理、我的面板、权限与宿主能力。克隆到本地 app 目录后按该仓库 README 构建。

## 插件

npm 发布正在等待账号二次认证，索引中的 `published: false` 表示尚不可从 npm 安装。

插件 npm 作用域为 `@mytools-all`；[database.json](plugins/database.json) 维护包名与版本索引。各插件可独立开发、测试和发布。

| 插件仓库 | npm 包 |
|---|---|
| [demo-hello](https://github.com/mytools-all/demo-hello) | [@mytools-all/demo-hello](https://www.npmjs.com/package/@mytools-all/demo-hello) |
| [mytools-calc](https://github.com/mytools-all/mytools-calc) | [@mytools-all/mytools-calc](https://www.npmjs.com/package/@mytools-all/mytools-calc) |
| [mytools-clipboard](https://github.com/mytools-all/mytools-clipboard) | [@mytools-all/mytools-clipboard](https://www.npmjs.com/package/@mytools-all/mytools-clipboard) |
| [mytools-color](https://github.com/mytools-all/mytools-color) | [@mytools-all/mytools-color](https://www.npmjs.com/package/@mytools-all/mytools-color) |
| [mytools-color-picker](https://github.com/mytools-all/mytools-color-picker) | [@mytools-all/mytools-color-picker](https://www.npmjs.com/package/@mytools-all/mytools-color-picker) |
| [mytools-ctool](https://github.com/mytools-all/mytools-ctool) | [@mytools-all/mytools-ctool](https://www.npmjs.com/package/@mytools-all/mytools-ctool) |
| [mytools-hello](https://github.com/mytools-all/mytools-hello) | [@mytools-all/mytools-hello](https://www.npmjs.com/package/@mytools-all/mytools-hello) |
| [mytools-ipconfig](https://github.com/mytools-all/mytools-ipconfig) | [@mytools-all/mytools-ipconfig](https://www.npmjs.com/package/@mytools-all/mytools-ipconfig) |
| [mytools-json](https://github.com/mytools-all/mytools-json) | [@mytools-all/mytools-json](https://www.npmjs.com/package/@mytools-all/mytools-json) |
| [mytools-markdown](https://github.com/mytools-all/mytools-markdown) | [@mytools-all/mytools-markdown](https://www.npmjs.com/package/@mytools-all/mytools-markdown) |
| [mytools-ocr](https://github.com/mytools-all/mytools-ocr) | [@mytools-all/mytools-ocr](https://www.npmjs.com/package/@mytools-all/mytools-ocr) |
| [mytools-rename](https://github.com/mytools-all/mytools-rename) | [@mytools-all/mytools-rename](https://www.npmjs.com/package/@mytools-all/mytools-rename) |
| [mytools-search](https://github.com/mytools-all/mytools-search) | [@mytools-all/mytools-search](https://www.npmjs.com/package/@mytools-all/mytools-search) |

## 本地布局

```text
mytools-home/
├── README.md
├── app/                    # mytools 独立仓库
└── plugins/
    ├── database.json       # 本仓库管理
    └── <插件名>/           # 每个插件独立仓库
```

根仓库只跟踪索引和介绍；app 和插件目录不作为子模块提交。克隆本仓库不会自动下载它们，请根据上面的链接分别克隆。宿主当前使用自带商店目录快照，npm 负责包分发；远程 JSON 动态同步尚未接入。
