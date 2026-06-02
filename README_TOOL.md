# SmartVision Studio · 批量尺寸转换工具

> 一个完全免费、开源、本地运行的批量图片尺寸转换神器  
> 原为 SmartVision Studio 项目的核心子模块，现独立发布，方便所有开发者和设计师使用

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Python 3.12+](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://www.python.org/)

## 为什么你需要这个工具？
- 上架 App 前，需要为 iOS/Android/Windows/macOS 生成十几个不同尺寸的图标，手动调整耗时且容易出错
- 电商运营要为淘宝、京东、Amazon 准备多种规格的商品主图，重复操作令人疲惫
- 需要将透明背景图片批量生成真正透明的 PNG（而非画在白底的“棋盘格”）
- 想导出标准 `.ico` 多尺寸图标，但现有工具要么收费，要么隐私堪忧

**这个工具让你：** 拖入图片 → 勾选平台预设 → 点击导出 → 全部自动完成，几秒钟搞定几十个文件。

---
## 🎯 工具效果（30秒演示）




## ✨ 功能一览

- 🔄 三种转换模式：一图 → 多尺寸 / 批量 → 多尺寸 / 多图 → 一尺寸
- 📦 内置 8 套行业标准预设：
  - iOS 图标、Android 自适应图标、Windows 桌面图标、macOS 图标
  - 网站 Favicon、社交媒体图片、浏览器插件截图、电商平台主图（淘宝/京东/拼多多/Amazon 等）
- ✏️ 灵活的尺寸定义：
  - 可只填宽或只填高，另一边自动等比计算
  - 支持锁定高宽相等（一键生成正方形尺寸）
- 🎨 强大的背景处理：
  - 自动检测并移除纯色背景，生成真·透明 PNG（非画上去的格子）
  - 添加圆角矩形背景，自定义颜色和半径
- 🖼️ 标准 ICO 导出：生成含 256px~16px 多尺寸的 Windows 图标文件，自动添加安全边距
- 📝 人性化命名系统：
  - 自定义基础文件名，支持占位符 `{basename}`、`{suffix}`、`{ext}`
  - 同名文件可选择覆盖、跳过或自动追加序号
- 🖥️ 清爽的图形界面：折叠面板、缩略图预览、滚轮滚动、实时文件列表
- 🔒 绝对隐私：完全本地运行，图片不上传任何服务器
- 🧩 核心引擎独立：可在其他 Python 项目中直接调用 `engine` 模块

---

## ⚡ 快速开始

### 环境
- Python 3.12 或更高版本
- 依赖库：`Pillow >= 9.2.0`

### 运行
```bash
# 克隆仓库
git clone https://github.com/你的用户名/批量尺寸转换工具.git
cd 批量尺寸转换工具

# 安装依赖
pip install -r requirements.txt

# 启动图形界面
python tools/batch_resize_gui.py
打包为独立 EXE（无需 Python 环境）
bash
pyinstaller --onefile --windowed --name BatchResize --icon=tools/assets/icon.ico --add-data "tools/assets;tools/assets" --add-data "data/presets;data/presets" --add-data "engine;engine" tools/batch_resize_gui.py
生成的 dist/BatchResize.exe 可直接运行。

加密引擎（可选）
运行 build_engine.bat，将 engine/size_converter.py 编译为 .pyd 二进制，保护核心算法。

🧪 作为引擎库使用
python
from engine.size_converter import batch_resize, export_as_ico, load_preset

preset = load_preset("data/presets/ios_icons.json")
batch_resize(
    input_paths=["logo.png"],
    target_sizes=preset["sizes"],
    output_dir="output",
    naming_rule="{basename}_{suffix}.png"
)
export_as_ico("logo.png", "logo.ico")
📁 项目结构
text
├── engine/                   # 核心引擎（无UI依赖）
│   └── size_converter.py
├── data/presets/             # 8 套预设 JSON
│   ├── ios_icons.json
│   ├── android_icons.json
│   ├── windows_icons.json
│   ├── macos_icons.json
│   ├── favicon.json
│   ├── social_media.json
│   ├── browser_store.json
│   └── ecommerce.json
├── tools/
│   ├── batch_resize_gui.py   # Tkinter 图形界面
│   └── assets/               # 图标资源
├── build_engine.bat           # 一键加密引擎
├── requirements.txt
├── README.md
└── LICENSE
📄 许可证与归属
本工具采用 GNU General Public License v3.0 (GPLv3) 许可。
你可以自由使用、修改、再发布，但必须保持开源，且衍生作品同样采用 GPLv3。
商业使用须遵守相同条款。

本项目源自 SmartVision Studio 的子模块，相关主项目可在这里找到。

🙏 支持与反馈
如果这个工具节省了你的时间，请给个 ⭐ Star，并分享给需要的朋友。
遇到问题或建议，欢迎提交 Issue。

Made with ❤️ by SmartVision Studio
