# Changelog

All notable changes to Chromagician, following [Keep a Changelog](https://keepachangelog.com) and [Semantic Versioning](https://semver.org).
Version 0.2.0 is built and type-checked, but not all of it has been run end to end yet.

## [0.2.0] - 2026-11-05

### Added

- **Macros:** `/save-macro name` turns a run into steps, and `/macro name` replays them with no AI, so it is fast, free and works without an API key.
- **Macro pause and repeat:** steps can wait for you to press Continue, or repeat (such as scrolling a feed) until you do.
- **Macro editing:** `/list-macro` shows a card to view, copy, edit as JSON and delete macros, and saved names are suggested as you type `/macro `.
- **Named playbooks:** `/save-playbook name` saves one, `/playbook name` has the agent do a task by following it, and `/list-playbook` manages them.
- **New tools:** `find`, `scroll`, `extract`, `web_search`, `look` (screenshot) and `ask_user` (a question with buttons).
- **Files from a page variable:** `create_file` can build CSV, JSON or markdown from data kept on the page, so long lists are never retyped.
- **More models:** Gemini, LM Studio, Ollama and any OpenAI-compatible address, with a model list fetched from the provider and a Test button.
- **Edit and Retry** for your messages and the agent's answers.
- **Clear errors:** a short, closable message for a rejected key, a rate limit, no credit, an unknown model or no connection; only transient failures are retried.
- **A log** of runs, model and tool calls, and errors, with Copy, Download and Clear in Settings.
- **Copy buttons** on macros and playbooks.

## 0.1.0 - 2026-11-04

First public release.

### Added

- **Side-panel agent** that runs in your own Chrome, streams its answer, and shows its reasoning and every tool step.
- **Browser control** through `chrome.debugger`: a compact page snapshot, and navigate, click, hover, fill, type, press keys, wait and handle dialogs.
- **Files as copy and download boxes,** page to markdown, a screenshot button and image attachments.
- **Saved conversations** that reopen with the panel, and a New chat button.
- **Memory and playbooks:** notes kept between chats (`/memory`) and recipes found by meaning with a small local model (`/playbook`).
- **Slash commands** with autocomplete and arguments.
- **A call budget** the agent knows about, and a progress report when it runs out.
- **Per-answer stats** (tokens in and out, speed, time).
- **Console access** (`run_script`, `read_console`), off by default.
- **A settings page,** including "Only the active tab".
- **Models:** Muse Spark Open on Baseten by default, plus Meta, OpenAI, Groq and a custom address.
- **Install** from a release zip or from source.
