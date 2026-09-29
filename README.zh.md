# Tomato

**[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)**

独立开发者。我做的是**原生桌面工具**，以及**把人类审批环节固化进流程的 AI 代理**。通常从我自己遇到的问题出发，再一路打磨到别人也能真正用起来的程度。

我做的东西大多处在应用与操作系统之间那一层：全局热键、辅助功能树、音频采集、菜单栏、权限弹窗。这一层演示效果差、在真实环境里容易出问题，但也正因如此才有意思。

---

## 主要项目

| 项目 | 简介 | 技术栈 |
| --- | --- | --- |
| **[voicekey](https://github.com/Tomato-1101/voicekey)** | 支持 macOS 与 Windows 的常驻语音输入工具。按下热键说话，转写结果直接落进你原本正在输入的窗口。STT 提供方可替换，支持流式与批量两种模式，并带自动更新。 | Swift / SwiftUI, Python, GitHub Actions |
| **[XNewsBot](https://github.com/Tomato-1101/XNewsBot)** | 每天早晚从 X 收集新闻，由 Claude 筛选、摘要后通过 LINE 推送的机器人。订阅的类别和推送时间可以直接和机器人对话设置。常驻服务器（Webhook 与推送调度）和 AI 整理分开运行。每天都在运行。 | Python, FastAPI, APScheduler, LINE Messaging API, Claude Code |
| **[XAgent](https://github.com/Tomato-1101/XAgent)** | 一个没有你批准就无法发帖的 X 运营代理。所有状态迁移都对照白名单校验，因此「机器人擅自发布」在代码层面就不可能发生——靠的是结构，而不是承诺。 | Python, FastAPI, React 19 |
| **[meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber)** | 把会议录音变成结构化笔记：降噪 → VAD → 转写 → 说话人分离 → 摘要。必须跑在 512MB 免费额度内这一约束，直接决定了整体架构。 | FastAPI, React, faster-whisper, Docker |
| **[menubar-drawer](https://github.com/Tomato-1101/menubar-drawer)** | 夺回被塞满的 macOS 菜单栏：把隐藏的状态项收进一个玻璃抽屉，并且不打开各应用的菜单，直接从辅助功能树中读取。 | Swift, AppKit, Accessibility API |

---

## 我的做法

- **把不起眼的那一半做完。** 权限弹窗、首次启动引导、等待时界面显示什么——这些才是用户真正会撞上的地方。只在理想路径下能跑通的功能，不算完成。
- **约束要写下来，而不是靠记。** 各仓库中都放有 `OVERVIEW.md` / `CLAUDE.md`，记录分支策略、设计决策，以及催生这些决策的失败。这些文件出现在公开仓库里是有意为之。
- **AI 代理是协作者，不是自动补全。** 我每天都在用 Claude Code 开发，包括一个约 5 万行的跨平台应用。真正有意思的工程问题在于设计「不允许代理做什么」——Hermes 和 XAgent 都建立在这个思路之上。
- **诚实的状态胜过好看的状态。** 如果东西还处在 pre-alpha，README 就写 pre-alpha。

---

## 技术栈

**语言** Swift · Python · TypeScript
**桌面** SwiftUI, AppKit, Accessibility API, CoreAudio, Electron
**Web** FastAPI, React 19, Next.js, Astro, Tailwind
**数据与基础设施** SQLite, Supabase, Cloudflare Workers/D1, Docker, GitHub Actions
**AI** Claude, Whisper 系 STT, Deepgram, 流式转写管线

---

<sub>这里都是个人项目。客户项目以及包含他人数据的内容一律保持私有。</sub>
