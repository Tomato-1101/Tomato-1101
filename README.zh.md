# Tomato

[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)

我做语音输入工具，以及盯加密货币和股票行情的机器人。代码基本都是用 Claude Code 写的。

### 语音

- [voicekey](https://github.com/Tomato-1101/voicekey)：macOS / Windows 的语音输入。按住快捷键说话，文字会直接输入到当前窗口。我每天都在用。网站：[voicekey.app](https://voicekey.app) (Swift, Python)
- [lecture-ai](https://github.com/Tomato-1101/lecture-ai)：在 iPhone 上录课并转成文字，可以就内容提问。(Swift, TypeScript, Cloudflare Workers)
- [english-live-tutor](https://github.com/Tomato-1101/english-live-tutor)：在浏览器里和实时语音 AI 练英语口语。(TypeScript, WebRTC)
- [meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber)：把会议录音转成带说话人标注的文字稿和摘要。(Python, faster-whisper)

### 行情

- [pump-watch](https://github.com/Tomato-1101/pump-watch)：监控 BSC 上的 meme 代币，开始上涨时发 Telegram 通知。其中一个检测通道直接从 BSC 日志读取兑换记录。只监控，不交易。(Python)
- [scalplab](https://github.com/Tomato-1101/scalplab)：记录日本股票的逐笔数据，用来回测日内交易规则。不下单。(Python)

### 其他

- [XAgent](https://github.com/Tomato-1101/XAgent)：起草 X 的帖子，我批准之前不会发出去。(Python, React)
- [XNewsBot](https://github.com/Tomato-1101/XNewsBot)：从 X 收集新闻，让 Claude 挑选并总结，通过 LINE 推送。(Python)
- [menubar-drawer](https://github.com/Tomato-1101/menubar-drawer)：把 macOS 菜单栏里太多的图标收进一个抽屉。(Swift)
