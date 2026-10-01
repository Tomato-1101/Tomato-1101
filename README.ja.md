# Tomato

[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)

音声入力のツールと、仮想通貨や株の値動きを見張るボットを作っています。コードはほぼ Claude Code で書いています。

ポートフォリオ: [zhao-yunbo.zhaounhaku.workers.dev](https://zhao-yunbo.zhaounhaku.workers.dev)

### 音声

- [voicekey](https://github.com/Tomato-1101/voicekey): macOS / Windows 用の音声入力です。ホットキーを押しながら話すと、入力中のウィンドウに文字が入ります。毎日使っています。サイト: [voicekey.vercel.app](https://voicekey.vercel.app) (Swift, Python)
- [lecture-ai](https://github.com/Tomato-1101/lecture-ai): iPhone で講義を録音して文字起こしし、内容について質問できるアプリです。(Swift, TypeScript, Cloudflare Workers)
- [english-live-tutor](https://github.com/Tomato-1101/english-live-tutor): ブラウザで音声 AI と英会話の練習ができるアプリです。(TypeScript, WebRTC)
- [meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber): 会議の録音から、話者付きの文字起こしと要約を作ります。(Python, faster-whisper)

### マーケット

- [pump-watch](https://github.com/Tomato-1101/pump-watch): BSC のミームトークンを監視して、上がり始めたものを Telegram に通知します。BSC のログからスワップを直接読む検知経路もあります。監視だけで、取引はしません。(Python)
- [scalplab](https://github.com/Tomato-1101/scalplab): 日本株のティックデータを記録して、デイトレのルールをバックテストします。発注はしません。(Python)

### その他

- [XAgent](https://github.com/Tomato-1101/XAgent): X の投稿を下書きします。承認するまで投稿されません。(Python, React)
- [XNewsBot](https://github.com/Tomato-1101/XNewsBot): X からニュースを集めて Claude に選ばせ、要約して LINE で配信します。(Python)
- [menubar-drawer](https://github.com/Tomato-1101/menubar-drawer): macOS のメニューバーに増えすぎたアイコンを引き出しにしまいます。(Swift)
