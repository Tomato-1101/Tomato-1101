# Tomato

**[English](README.md) | [日本語](README.ja.md) | [中文](README.zh.md)**

Independent developer. I build **native desktop tools** and **AI agents that keep a human in the loop** — usually starting from a problem I hit myself, then polishing it until it holds up as a real product.

Most of what I ship lives at the awkward layer between an app and the operating system: global hotkeys, accessibility trees, audio capture, menu bars, permission prompts. It is the part that demos badly and breaks in the field, which is exactly why I find it interesting.

---

## Featured work

| Project | What it is | Stack |
| --- | --- | --- |
| **[voicekey](https://github.com/Tomato-1101/voicekey)** | Hotkey-driven voice input for macOS and Windows. Press a key, speak, and the transcript lands in whatever window you were already typing into. Pluggable STT providers, streaming and batch modes, auto-update. | Swift / SwiftUI, Python, GitHub Actions |
| **[XNewsBot](https://github.com/Tomato-1101/XNewsBot)** | A LINE bot that collects news from X every morning and evening, has Claude curate and summarize it, and delivers it on a schedule each subscriber sets by chatting with the bot. The always-on server (webhook + scheduler) and the scheduled AI curation run as separate parts. Running daily. | Python, FastAPI, APScheduler, LINE Messaging API, Claude Code |
| **[XAgent](https://github.com/Tomato-1101/XAgent)** | A posting agent for X that cannot post without you. Every state transition is validated against an allow-list, so "the bot published something on its own" is a code-level impossibility, not a promise. | Python, FastAPI, React 19 |
| **[meeting-transcriber](https://github.com/Tomato-1101/meeting-transcriber)** | Meeting audio to structured notes — denoise, VAD, transcribe, diarize, summarize. Tuned to survive inside a 512 MB free tier, which shaped most of the architecture. | FastAPI, React, faster-whisper, Docker |
| **[menubar-drawer](https://github.com/Tomato-1101/menubar-drawer)** | Reclaims a crowded macOS menu bar by collapsing hidden status items into a glass drawer — read straight from the accessibility tree, without opening each app's menu. | Swift, AppKit, Accessibility API |

---

## How I work

- **Ship the unglamorous half.** Permission dialogs, first-run onboarding, what the UI shows while it is waiting — the parts users actually hit. A feature that works only on the happy path is not finished.
- **Constraints get written down, not remembered.** Repositories carry an `OVERVIEW.md` / `CLAUDE.md` describing the branch policy, the design decisions, and the mistakes that produced them. Some of those files are in these repos; they are there on purpose.
- **AI agents are collaborators, not autocomplete.** I develop with Claude Code daily, including on a ~50k-line cross-platform app. The interesting engineering is in deciding what the agent is *not* allowed to do — which is the same idea Hermes and XAgent are both built around.
- **Honest status over impressive status.** If something is pre-alpha, the README says pre-alpha.

---

## Tech

**Languages** Swift · Python · TypeScript
**Desktop** SwiftUI, AppKit, Accessibility API, CoreAudio, Electron
**Web** FastAPI, React 19, Next.js, Astro, Tailwind
**Data & infra** SQLite, Supabase, Cloudflare Workers/D1, Docker, GitHub Actions
**AI** Claude, Whisper-family STT, Deepgram, streaming transcription pipelines

---

<sub>Repositories here are personal projects. Client work and anything containing other people's data stays private.</sub>
