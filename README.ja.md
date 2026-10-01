# Tomato

**[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)**

**聞く**ソフトウェアと**見張る**ソフトウェアを作っています。話した言葉を必要な場所にそのまま届ける音声インターフェースと、ノイズだらけの市場からシグナルを拾うリアルタイムのパイプライン。そして、人間の承認なしには動けない AI エージェント。ほとんどは自分のマシンで毎日動いています。

---

## 音声

| プロジェクト | 内容 | 技術 |
| --- | --- | --- |
| **[voicekey](https://github.com/Tomato-1101/voicekey)** | macOS / Windows 対応の常駐型音声入力ツール。ホットキーを押して話すと、いま入力していたウィンドウにそのまま文字が入る。STT プロバイダ差し替え可・ストリーミング/バッチ両対応・自動更新つき。 | Swift / SwiftUI, Python, GitHub Actions |
| **[lecture-ai](https://github.com/Tomato-1101/lecture-ai)** | iPhone で講義を録音するアプリ。ネイティブの録音部は画面ロック中も録り続け、タイマーではなく話の切れ目で区切り、端末に保存してから送る。文字起こしは 4 つの Whisper エンジンを順に試し、幻覚（存在しない文）を除去する。質問への回答は文字起こしと資料だけを根拠にする。 | Swift (AVAudioSession), Cloudflare Workers + D1, React PWA, Python |
| **[english-live-tutor](https://github.com/Tomato-1101/english-live-tutor)** | full-duplex の音声モデルと WebRTC でつなぐ、リアルタイムの英会話レッスン。画面表示は委譲の往復で行い、話者交代はプロンプトで制御し、秒課金に合わせてセッションの開閉を設計した。 | React 19, Cloudflare Workers + D1, WebRTC |
| **[meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber)** | 会議音声を構造化されたノートに変換する（ノイズ除去 → VAD → 文字起こし → 話者分離 → 要約）。512MB の無料枠で動かし切る前提で設計した。 | FastAPI, React, faster-whisper, Docker |

## マーケット・オンチェーン

| プロジェクト | 内容 | 技術 |
| --- | --- | --- |
| **[pump-watch](https://github.com/Tomato-1101/pump-watch)** | BSC のミームトークンを監視し、明確に上がり始めたものを Telegram に通知する。トレンドでの確定、API ポーリング、チェーンのログから PancakeSwap / four.meme のスワップを直接デコードする経路の 3 系統。レート制限の残量は複数プロセスで共有し、SQLite 1 ファイルに複数の書き手が書く。監視専用で、鍵も持たず取引もしない。テスト 508 件。 | Python（標準ライブラリのみ）, BSC JSON-RPC, SQLite WAL, Telegram Bot API |
| **[scalplab](https://github.com/Tomato-1101/scalplab)** | 日本株デイトレードのティック単位の検証環境。落ちても欠けないティック録画、ベクトル化経路と突き合わせたティック再生バックテスト、ゴールデン値テスト付きの自前インジケーター、毎晩のウォークフォワード評価。発注機能はない。テスト 290 件。 | Python, pandas, parquet, WebSocket（RFC 6455、標準ライブラリ） |

## 人間の承認を挟むエージェント

| プロジェクト | 内容 | 技術 |
| --- | --- | --- |
| **[XAgent](https://github.com/Tomato-1101/XAgent)** | 承認なしには投稿できない X 運用エージェント。状態遷移をすべて許可リストで検証しているので、「ボットが勝手に投稿した」はコードレベルで起こり得ない。約束ではなく構造で担保している。 | Python, FastAPI, React 19 |
| **[XNewsBot](https://github.com/Tomato-1101/XNewsBot)** | X から朝と夜にニュースを集め、Claude が選別して、購読者ごとの時刻に LINE で配信するボット。ヘッドレスで動く AI の工程は、プロンプトインジェクション対策として使えるツールを絞っている。毎日運用中。 | Python, FastAPI, APScheduler, LINE Messaging API |
| **[menubar-drawer](https://github.com/Tomato-1101/menubar-drawer)** | 過密になった macOS のメニューバーを、ガラスの引き出しにまとめる常駐アプリ。隠れたステータス項目をアクセシビリティツリーから直接読む。 | Swift, AppKit, Accessibility API |

---

## 開発の姿勢

- **地味な半分をちゃんと作る。** 権限ダイアログ、バックグラウンドの音声セッション、再接続、レート制限、待っている間に画面が何を出すか。デモ映えせず、実環境で壊れるのはそこです。
- **測ってから言う。** 検知ルールは保存したデータを再生して前後の結果を比べてから変えます。README には、実行した結果と数えただけの値を分けて書きます。
- **エージェントには信頼ではなく境界を。** Claude Code を毎日使って開発しています。面白いのは「エージェントに何を*させないか*」を設計する部分です。
- **見栄えより正直なステータス。** pre-alpha なら README に pre-alpha と書きます。

---

## 技術スタック

**言語** Swift · Python · TypeScript
**音声** AVAudioSession, CoreAudio, WebRTC, Whisper (Groq, whisper.cpp, faster-whisper), Deepgram, VAD, 話者分離, リアルタイム音声モデル
**マーケット** BSC JSON-RPC のログデコード, GMGN / DexScreener / GeckoTerminal, ティックデータ, parquet, ウォークフォワード検証
**デスクトップ** SwiftUI, AppKit, Accessibility API, Electron
**Web・インフラ** FastAPI, React 19, Next.js, Cloudflare Workers / D1 / KV, SQLite, Supabase, Docker, GitHub Actions
**AI** Claude（Claude Code、ヘッドレス `claude -p`）, OpenAI リアルタイム音声

---

<sub>ここにあるのは個人プロジェクトです。クライアント案件や第三者のデータを含むものは非公開にしています。</sub>
