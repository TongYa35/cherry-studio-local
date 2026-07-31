<h1 align="center">🍒 Cherry Studio（个人适配版）</h1>

<p align="center"><strong>为个人电脑使用场景优化的 Cherry Studio 定制版本</strong></p>

<div align="center">

[![][license-shield]][license-link]

</div>

---

## 📌 项目简介

本项目基于开源项目 [CherryHQ/cherry-studio](https://github.com/CherryHQ/cherry-studio) 进行二次适配，针对**个人电脑的日常使用场景**做了针对性优化，保留了 Cherry Studio 的全部核心能力（多模型对话、知识库、翻译、绘画等），同时让本地开发、构建和运行更加简便。

> 原项目：<https://github.com/CherryHQ/cherry-studio>
> 本仓库为个人学习与使用目的维护的适配分支，遵循上游 [AGPL-3.0](LICENSE) 协议。

---

## 🎯 适配内容

本版本在官方 Cherry Studio 基础上，主要做了以下适配：

### 1. 🗂️ 数据目录自定义

- 新增环境变量 `CS_USER_DATA_PATH`，可将应用数据（缓存、配置、本地存储等）**独立存放于源码目录**，与系统默认路径解耦
- 数据默认保存在项目根目录的 `cherry-studio-data/` 文件夹，方便备份与迁移

### 2. 🚀 一键启动脚本

提供多种启动脚本，覆盖不同的使用场景：

| 脚本 | 适用场景 |
|------|---------|
| `start-fast.bat` / `start-fast.ps1` | 🚀 最快启动（直接运行打包后的应用） |
| `start-quick.bat` / `start-quick.ps1` | ⚡ 快速启动（推荐日常使用） |
| `start.bat` / `start.ps1` | 🔧 完整启动（含原生模块重建） |
| `start-dev.bat` | 🛠️ 开发模式（Vite 热更新） |
| `start-fast.vbs` | 🤫 静默启动（无控制台窗口） |

> ⚠️ 以上脚本为个人使用而生，均已加入 `.gitignore`，不会随代码提交。

### 3. 📦 开箱即用的打包构建

- 已配置本地打包产物目录（`dist/win-unpacked`），构建后可直接通过启动脚本运行
- 内存优化：启动时默认分配 `NODE_OPTIONS=--max-old-space-size=8000`，提升大型对话场景下的稳定性

---

## ✨ 核心功能（继承自 Cherry Studio）

- 🌐 **多模型支持**：OpenAI、Gemini、Anthropic、Claude、本地模型（Ollama / LM Studio）等
- 🤖 **AI 助手**：300+ 预置助手，支持自定义助手与多模型同时对话
- 📄 **文档处理**：支持文本、图片、Office、PDF 等多格式文件
- 📝 **知识库**：本地向量库，支持知识库问答
- 🖼️ **AI 绘画**：内置绘画功能
- 🎨 **个性化**：明暗主题、透明窗口、完全 Markdown 渲染
- 🔌 **生态扩展**：MCP 服务、小程序、插件支持

---

## 🛠️ 本地开发

```bash
# 安装依赖
pnpm install

# 开发模式（热更新）
pnpm dev

# 构建打包
pnpm build

# 运行打包产物（Windows）
pnpm start
```

> 详细开发指南请参考 [docs/guides/development.md](docs/guides/development.md)

---

## 📁 目录结构

```
cherry-studio/
├── cherry-studio-data/    # 本地运行数据（已 gitignore）
├── dist/                  # 打包产物
├── src/                   # 源代码
├── start-*.bat|ps1|vbs    # 本地启动脚本（已 gitignore）
└── ...
```

---

## 📄 许可证

本项目基于 [AGPL-3.0](LICENSE) 协议开源，所有内容遵循上游 Cherry Studio 的开源许可要求。

---

<p align="center">Made with ❤️ for personal use · 基于 <a href="https://github.com/CherryHQ/cherry-studio">CherryHQ/cherry-studio</a></p>

[license-shield]: https://img.shields.io/badge/License-AGPL--3.0-blue.svg
[license-link]: LICENSE
