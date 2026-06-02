# SmartVision Studio

> 🧠 A local-first, AI-powered image toolbox. Smart crop, repair, upscale, and organize your photos — all offline, all private.

**SmartVision Studio** 是一款本地优先、AI 驱动的智能图片处理工具箱。它集成了图库管理、智能裁剪、AI 修复、格式转换、批量输出等核心功能，所有数据处理完全在本地完成，无需上传至任何云端服务器，确保你的隐私安全。

---

## ✨ 核心亮点

- 🔒 **本地优先，隐私至上**：所有图片处理均在你的电脑上完成，绝不上传任何数据。
- 🤖 **AI 智能增强**：集成 CLIP 智能分类、LaMa 去水印、Real-ESRGAN 高清修复、RMBG-2.0 智能抠图等先进 AI 模型。
- 🧩 **六大模块，一站式工作流**：图库 → 裁剪 → 修复 → 调色 → 输出 → 拼接，覆盖从浏览到导出的完整流程。
- 🌓 **深浅主题切换**：精心设计的浅灰与深色双主题，适配不同使用环境。
- 💾 **状态记忆与恢复**：自动保存工作进度，下次启动无缝衔接。
- ⚡ **批量处理**：支持预设工作流，一键批量执行多步操作。

---

## 🚀 快速开始

### 环境要求

- Python 3.12+
- Windows 10/11（macOS 和 Linux 可运行，但部分功能未完全测试）
- NVIDIA 显卡（推荐 4GB 显存以上，非必须但可显著提升 AI 处理速度）

### 安装与运行

```bash
# 1. 克隆仓库
git clone https://github.com/lOVE-o837/SmartVision-Studio.git
cd SmartVision-Studio

# 2. 安装依赖
pip install -r requirements.txt

# 3. 启动程序
python src/main.py
📐 功能模块
模块	功能简介	状态
📷 图库	智能相册管理、AI 标签分类、快捷收藏、Hover 放大预览	✅
✂️ 裁剪	三工具自由裁剪、自动裁剪、AI 主体检测辅助线	✅
🛠️ 修复	AI 去水印、AI 高清修复、AI 智能抠图	🚧
🎨 调色	AI 风格迁移、HDR 合成、色彩空间转换	📅
📤 输出	多尺寸批量转换、格式互转、水印添加、批量压缩	🚧
🖼️ 拼接	横/纵向无缝拼接、图片转 PDF	📅
✅ 已完成　🚧 开发中　📅 计划中

🛠️ 技术栈
层级	技术
UI 框架	PySide6 (Qt for Python)
图像处理	OpenCV, Pillow
AI 模型	CLIP, EasyOCR, LaMa, Real-ESRGAN, RMBG-2.0, MiniCPM-V
样式主题	ttkbootstrap + 自定义 QSS
数据存储	JSON (本地文件)
📅 路线图
V1.0 — 基础裁剪工具 + 深浅主题 + 记忆功能

V2.0 — PySide6 迁移 + 智能图库 + AI 修复 + 批量输出

V3.0 — 用户私人 AI 模型微调 + 云端同步

🤝 贡献指南
欢迎提交 Issue 和 Pull Request！请先阅读 CONTRIBUTING.md。

📄 许可证
本项目基于 GNU General Public License v3.0 (GPLv3) 许可开源。详见 LICENSE 文件。
