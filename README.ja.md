# Tomato

**[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)**

個人開発者。**ネイティブのデスクトップツール**と、**人間の承認を挟むことを前提にした AI エージェント**を作っています。だいたいは自分が困ったことから始めて、他人が使える水準まで仕上げるところまでやります。

作っているものの多くは、アプリと OS の境目という扱いにくい層にあります。グローバルホットキー、アクセシビリティツリー、音声キャプチャ、メニューバー、権限ダイアログ。デモ映えせず、実環境で壊れる領域ですが、だからこそ面白いと思っています。

---

## 主なプロジェクト

| プロジェクト | 内容 | 技術 |
| --- | --- | --- |
| **[voicekey](https://github.com/Tomato-1101/voicekey)** | macOS / Windows 対応の常駐型音声入力ツール。ホットキーを押して話すと、いま入力していたウィンドウにそのまま文字が入る。STT プロバイダ差し替え可・ストリーミング/バッチ両対応・自動更新つき。 | Swift / SwiftUI, Python, GitHub Actions |
| **[XNewsBot](https://github.com/Tomato-1101/XNewsBot)** | X から朝と夜にニュースを集め、Claude が選別・要約して LINE で配信するボット。受け取るジャンルと配信時刻は Bot との会話で設定できる。常駐サーバー（Webhook と配信スケジューラー）と AI のキュレーションを別々に動かす構成。毎日運用中。 | Python, FastAPI, APScheduler, LINE Messaging API, Claude Code |
| **[XAgent](https://github.com/Tomato-1101/XAgent)** | 承認なしには投稿できない X 運用エージェント。状態遷移をすべて許可リストで検証しているので、「ボットが勝手に投稿した」はコードレベルで起こり得ない。約束ではなく構造で担保している。 | Python, FastAPI, React 19 |
| **[meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber)** | 会議音声を構造化されたノートに変換する（ノイズ除去 → VAD → 文字起こし → 話者分離 → 要約）。512MB の無料枠で動かし切るという制約が、そのまま設計を決めた。 | FastAPI, React, faster-whisper, Docker |
| **[menubar-drawer](https://github.com/Tomato-1101/menubar-drawer)** | 過密になった macOS のメニューバーを取り戻す常駐アプリ。隠れたステータス項目をガラスの引き出しにまとめる。各アプリのメニューを開かず、アクセシビリティツリーから直接読む。 | Swift, AppKit, Accessibility API |

---

## 開発の姿勢

- **地味な半分をちゃんと作る。** 権限ダイアログ、初回セットアップ、待っている間に画面が何を出すか。ユーザーが実際にぶつかるのはそこです。ハッピーパスだけ動く機能は、完成していないと考えています。
- **制約は記憶ではなく記録する。** 各リポジトリに `OVERVIEW.md` / `CLAUDE.md` を置き、ブランチ運用・設計判断・そこに至った失敗を残しています。これらのファイルが公開リポジトリに入っているのは意図的です。
- **AI エージェントは補完ではなく共同開発者。** Claude Code を日常的に使い、5万行規模のクロスプラットフォームアプリもこの体制で開発しています。面白いのは「エージェントに何を*させないか*」を設計する部分で、Hermes と XAgent はどちらもその発想でできています。
- **見栄えより正直なステータス。** pre-alpha なら README に pre-alpha と書きます。

---

## 技術スタック

**言語** Swift · Python · TypeScript
**デスクトップ** SwiftUI, AppKit, Accessibility API, CoreAudio, Electron
**Web** FastAPI, React 19, Next.js, Astro, Tailwind
**データ・インフラ** SQLite, Supabase, Cloudflare Workers/D1, Docker, GitHub Actions
**AI** Claude, Whisper 系 STT, Deepgram, ストリーミング文字起こし基盤

---

<sub>ここにあるのは個人プロジェクトです。クライアント案件や第三者のデータを含むものは非公開にしています。</sub>
