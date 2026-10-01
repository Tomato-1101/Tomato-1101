# Tomato

**[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)**

我做两类软件：**会听的**和**会盯的**。一类是把说出的话直接送到需要它的地方的语音界面，另一类是从充满噪声的市场里捞出信号的实时管线。再加上没有人批准就无法行动的 AI 代理。它们大多每天都在我自己的机器上运行。

---

## 语音

| 项目 | 简介 | 技术栈 |
| --- | --- | --- |
| **[voicekey](https://github.com/Tomato-1101/voicekey)** | 支持 macOS 与 Windows 的常驻语音输入工具。按下热键说话，转写结果直接落进你原本正在输入的窗口。STT 提供方可替换，支持流式与批量两种模式，并带自动更新。 | Swift / SwiftUI, Python, GitHub Actions |
| **[lecture-ai](https://github.com/Tomato-1101/lecture-ai)** | 在 iPhone 上录制课堂的应用。原生录音模块在锁屏后也持续录音，按停顿而不是按定时切分片段，先落盘再上传。转写在 4 个 Whisper 引擎之间依次回退，并过滤幻觉文本；问答只以转写和资料为依据。 | Swift (AVAudioSession), Cloudflare Workers + D1, React PWA, Python |
| **[english-live-tutor](https://github.com/Tomato-1101/english-live-tutor)** | 通过 WebRTC 连接全双工语音模型的实时英语口语课。屏幕工具通过委派往返调用，话轮控制写在提示词里，会话的开关围绕按秒计费来设计。 | React 19, Cloudflare Workers + D1, WebRTC |
| **[meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber)** | 把会议录音变成结构化笔记：降噪 → VAD → 转写 → 说话人分离 → 摘要。以跑在 512MB 免费额度内为前提设计。 | FastAPI, React, faster-whisper, Docker |

## 市场与链上

| 项目 | 简介 | 技术栈 |
| --- | --- | --- |
| **[pump-watch](https://github.com/Tomato-1101/pump-watch)** | 监控 BSC 上的 meme 代币，在明显开始拉升时推送到 Telegram。三条检测通道：热榜确认、API 轮询、直接从链上日志解码 PancakeSwap / four.meme 的兑换。限流额度在多个进程之间共享，多个写入方共用一个 SQLite 文件。只做监控：不持有私钥，也不交易。508 个测试。 | Python（仅标准库）, BSC JSON-RPC, SQLite WAL, Telegram Bot API |
| **[scalplab](https://github.com/Tomato-1101/scalplab)** | 日本股票日内交易的逐笔研究环境：崩溃也不丢数据的逐笔录制、与向量化路径对照的逐笔回放回测、带黄金值测试的自研指标，以及每晚的滚动前推评估。没有下单功能。290 个测试。 | Python, pandas, parquet, WebSocket（RFC 6455，标准库） |

## 有人类把关的代理

| 项目 | 简介 | 技术栈 |
| --- | --- | --- |
| **[XAgent](https://github.com/Tomato-1101/XAgent)** | 一个没有你批准就无法发帖的 X 运营代理。所有状态迁移都对照白名单校验，因此「机器人擅自发布」在代码层面就不可能发生——靠的是结构，而不是承诺。 | Python, FastAPI, React 19 |
| **[XNewsBot](https://github.com/Tomato-1101/XNewsBot)** | 每天早晚从 X 收集新闻，由 Claude 筛选，按每位订阅者设定的时间通过 LINE 推送。无人值守运行的 AI 环节收窄了可用工具，以防提示词注入。每天都在运行。 | Python, FastAPI, APScheduler, LINE Messaging API |
| **[menubar-drawer](https://github.com/Tomato-1101/menubar-drawer)** | 把塞满的 macOS 菜单栏收进一个玻璃抽屉，直接从辅助功能树读取隐藏的状态项。 | Swift, AppKit, Accessibility API |

---

## 我的做法

- **把不起眼的那一半做完。** 权限弹窗、后台音频会话、重连、限流、等待时界面显示什么——演示效果差、在真实环境里会坏的正是这些地方。
- **先测量，再下结论。** 检测规则要先回放已存数据、比较改动前后的结果再改；README 里把实际运行的结果和只是数出来的数字分开写。
- **给代理的是边界，不是信任。** 我每天都用 Claude Code 开发。真正有意思的工程问题在于设计「不允许代理做什么」。
- **诚实的状态胜过好看的状态。** 如果东西还处在 pre-alpha，README 就写 pre-alpha。

---

## 技术栈

**语言** Swift · Python · TypeScript
**语音** AVAudioSession, CoreAudio, WebRTC, Whisper (Groq, whisper.cpp, faster-whisper), Deepgram, VAD, 说话人分离, 实时语音模型
**市场** BSC JSON-RPC 日志解码, GMGN / DexScreener / GeckoTerminal, 逐笔数据, parquet, 滚动前推回测
**桌面** SwiftUI, AppKit, Accessibility API, Electron
**Web 与基础设施** FastAPI, React 19, Next.js, Cloudflare Workers / D1 / KV, SQLite, Supabase, Docker, GitHub Actions
**AI** Claude（Claude Code、无头 `claude -p`）, OpenAI 实时语音

---

<sub>这里都是个人项目。客户项目以及包含他人数据的内容一律保持私有。</sub>
