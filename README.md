# Tomato

**[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)**

I build software that **listens** and software that **watches**: voice interfaces that put speech exactly where you need it, and real-time pipelines that pull a signal out of noisy markets — plus AI agents that are not allowed to act without a human. Most of it runs every day on my own machines.

---

## Voice

| Project | What it is | Stack |
| --- | --- | --- |
| **[voicekey](https://github.com/Tomato-1101/voicekey)** | Hotkey-driven voice input for macOS and Windows. Press a key, speak, and the transcript lands in whatever window you were typing into. Pluggable STT providers, streaming and batch modes, auto-update. | Swift / SwiftUI, Python, GitHub Actions |
| **[lecture-ai](https://github.com/Tomato-1101/lecture-ai)** | Records lectures on iPhone with a native recorder that keeps capturing in the background, cuts segments on pauses instead of a timer, and uploads disk-first. Transcription falls back across four Whisper engines with a hallucination filter; answers are grounded only in the transcript. | Swift (AVAudioSession), Cloudflare Workers + D1, React PWA, Python |
| **[english-live-tutor](https://github.com/Tomato-1101/english-live-tutor)** | A real-time voice English tutor over WebRTC with a full-duplex voice model: screen tools through a delegation round trip, turn-taking enforced in the prompt, and a session lifecycle built around per-second billing. | React 19, Cloudflare Workers + D1, WebRTC |
| **[meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber)** | Meeting audio to structured notes — denoise, VAD, transcribe, diarize, summarize — tuned to fit inside a 512 MB free tier. | FastAPI, React, faster-whisper, Docker |

## Markets and on-chain

| Project | What it is | Stack |
| --- | --- | --- |
| **[pump-watch](https://github.com/Tomato-1101/pump-watch)** | Watches BSC meme tokens and alerts on Telegram when one is clearly taking off. Three detection lanes — trending confirmation, API polling, and decoding PancakeSwap / four.meme swaps straight from chain logs — sharing rate-limit budgets across processes and one SQLite file across writers. Monitor only: no keys, no trades. 508 tests. | Python (stdlib only), BSC JSON-RPC, SQLite WAL, Telegram Bot API |
| **[scalplab](https://github.com/Tomato-1101/scalplab)** | Tick-level research lab for Japanese equities: a crash-safe tick recorder, a tick-replay backtest checked against a vectorised path, indicators written from scratch with golden-value tests, and nightly walk-forward evaluation. Places no orders. 290 tests. | Python, pandas, parquet, WebSocket (RFC 6455, stdlib) |

## Agents with a human in the loop

| Project | What it is | Stack |
| --- | --- | --- |
| **[XAgent](https://github.com/Tomato-1101/XAgent)** | A posting agent for X that cannot post without you. Every state transition is validated against an allow-list, so "the bot published on its own" is impossible at the code level, not a promise. | Python, FastAPI, React 19 |
| **[XNewsBot](https://github.com/Tomato-1101/XNewsBot)** | A LINE bot that collects news from X twice a day, has Claude curate it, and delivers on each subscriber's own schedule. The headless AI step runs with a narrowed tool set against prompt injection. Running daily. | Python, FastAPI, APScheduler, LINE Messaging API |
| **[menubar-drawer](https://github.com/Tomato-1101/menubar-drawer)** | Collapses a crowded macOS menu bar into a glass drawer, reading hidden status items straight from the accessibility tree. | Swift, AppKit, Accessibility API |

---

## How I work

- **Ship the unglamorous half.** Permission dialogs, background audio sessions, reconnects, rate limits, what the UI shows while it waits — the parts that demo badly and break in the field.
- **Measure, then claim.** Detection rules are changed by replaying stored data and comparing results before and after; READMEs say what was run and what was only counted.
- **Agents get boundaries, not trust.** I develop with Claude Code every day. The interesting engineering is deciding what an agent is *not* allowed to do.
- **Honest status over impressive status.** If something is pre-alpha, the README says so.

---

## Tech

**Languages** Swift · Python · TypeScript
**Voice** AVAudioSession, CoreAudio, WebRTC, Whisper (Groq, whisper.cpp, faster-whisper), Deepgram, VAD, diarization, realtime voice models
**Markets** BSC JSON-RPC log decoding, GMGN / DexScreener / GeckoTerminal, tick data, parquet, walk-forward backtesting
**Desktop** SwiftUI, AppKit, Accessibility API, Electron
**Web and infra** FastAPI, React 19, Next.js, Cloudflare Workers / D1 / KV, SQLite, Supabase, Docker, GitHub Actions
**AI** Claude (Claude Code, headless `claude -p`), OpenAI realtime voice

---

<sub>Repositories here are personal projects. Client work and anything containing other people's data stays private.</sub>
