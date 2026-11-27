# MyTools 项目索引

Windows 插件工具箱，宿主使用 Tauri 2、Vue 3 和 Rust。宿主与每个插件各自维护独立 Git 仓库，项目代码采用 MIT，第三方代码保留自身许可。

## 宿主

[mytools](https://github.com/mytools-all/mytools) 提供启动器、插件管理、资源管理、鼠标中键面板和宿主能力。当前版本 0.2.0，Windows x64 安装包与免安装包见 [正式版下载](https://github.com/mytools-all/mytools/releases/latest)。主程序只通过 GitHub Release 发布。

## 插件

共 15 个插件可通过 npm 安装。包名和版本以 [plugins/database.json](plugins/database.json) 为准；published:true 表示已核验对应版本可以查询和下载。

| 插件 | 版本 | GitHub | npm |
|---|---|---|---|
| MyTools Demo | 0.1.2 | [mytools-demo](https://github.com/mytools-all/mytools-demo) | [@mytools-all/mytools-demo](https://www.npmjs.com/package/@mytools-all/mytools-demo) |
| 计算稿纸 | 0.1.2 | [mytools-calc](https://github.com/mytools-all/mytools-calc) | [@mytools-all/mytools-calc](https://www.npmjs.com/package/@mytools-all/mytools-calc) |
| 系统剪贴板 | 0.1.2 | [mytools-clipboard](https://github.com/mytools-all/mytools-clipboard) | [@mytools-all/mytools-clipboard](https://www.npmjs.com/package/@mytools-all/mytools-clipboard) |
| 颜色助手 | 0.1.2 | [mytools-color](https://github.com/mytools-all/mytools-color) | [@mytools-all/mytools-color](https://www.npmjs.com/package/@mytools-all/mytools-color) |
| 屏幕取色器 | 0.1.2 | [mytools-color-picker](https://github.com/mytools-all/mytools-color-picker) | [@mytools-all/mytools-color-picker](https://www.npmjs.com/package/@mytools-all/mytools-color-picker) |
| Ctool | 0.1.1 | [mytools-ctool](https://github.com/mytools-all/mytools-ctool) | [@mytools-all/mytools-ctool](https://www.npmjs.com/package/@mytools-all/mytools-ctool) |
| ipconfig | 0.1.1 | [mytools-ipconfig](https://github.com/mytools-all/mytools-ipconfig) | [@mytools-all/mytools-ipconfig](https://www.npmjs.com/package/@mytools-all/mytools-ipconfig) |
| JSON 编辑器 | 0.1.1 | [mytools-json](https://github.com/mytools-all/mytools-json) | [@mytools-all/mytools-json](https://www.npmjs.com/package/@mytools-all/mytools-json) |
| Markdown 编辑器 | 0.1.2 | [mytools-markdown](https://github.com/mytools-all/mytools-markdown) | [@mytools-all/mytools-markdown](https://www.npmjs.com/package/@mytools-all/mytools-markdown) |
| 图片 OCR | 0.2.1 | [mytools-ocr](https://github.com/mytools-all/mytools-ocr) | [@mytools-all/mytools-ocr](https://www.npmjs.com/package/@mytools-all/mytools-ocr) |
| 文件批量重命名 | 0.1.1 | [mytools-rename](https://github.com/mytools-all/mytools-rename) | [@mytools-all/mytools-rename](https://www.npmjs.com/package/@mytools-all/mytools-rename) |
| 本地搜索 | 0.1.2 | [mytools-search](https://github.com/mytools-all/mytools-search) | [@mytools-all/mytools-search](https://www.npmjs.com/package/@mytools-all/mytools-search) |
| 我的日历 | 0.2.1 | [mytools-calendar](https://github.com/mytools-all/mytools-calendar) | [@mytools-all/mytools-calendar](https://www.npmjs.com/package/@mytools-all/mytools-calendar) |
| 打卡 | 0.1.1 | [mytools-clock](https://github.com/mytools-all/mytools-clock) | [@mytools-all/mytools-clock](https://www.npmjs.com/package/@mytools-all/mytools-clock) |
| 电脑助手 | 0.1.2 | [mytools-computer-assistant](https://github.com/mytools-all/mytools-computer-assistant) | [@mytools-all/mytools-computer-assistant](https://www.npmjs.com/package/@mytools-all/mytools-computer-assistant) |

## MyTools 兼容范围

本轮 15 个插件均声明支持 MyTools >=0.2.0 <0.3.0，插件 API v1。0.1.0 用户请先升级主程序；旧版可能忽略兼容声明。不兼容的新版本不会覆盖当前插件和数据。

## 本地布局

建议将三个目录并列放置，每个插件保持独立仓库：

```text
MyTools/
├── mytools/
├── mytools-home/
└── plugins/
    └── <插件名>/
```

mytools-home 只维护项目说明和插件索引，不包含宿主或插件源码。运行中的插件目录由宿主配置决定，与源码目录相互独立。修改源码后需要重新打包安装；插件可单独更新。
