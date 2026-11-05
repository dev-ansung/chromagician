<p align="center"><img src="docs/icon.png" width="128" height="128" alt="Chromagician: a magic wand with four colourful stars"></p>

# Chromagician

An autonomous browser agent in Chrome's side panel. It works in **your own browser**, on the tab you are on, with your logins. Ask in plain
words and it reads the page, clicks, types, collects data and saves files. Powered by **Muse Spark Open**, or any OpenAI-compatible model,
including one running on your own computer.

**License:** [MIT](LICENSE) · **What's new:** [CHANGELOG](CHANGELOG.md)

## Install

1. Download the zip from the [latest release](https://github.com/dev-ansung/chromagician/releases/latest) and unzip it.
2. Open `chrome://extensions`, turn on **Developer mode**, click **Load unpacked** and choose the unzipped folder.
3. Pin **Chromagician** and click it to open the side panel.
4. Click the gear, pick a provider, and paste its API key (Baseten by default). Press **Test** to check it.
5. Ask something: "What's on this page?", "List every link as a CSV", "Save this page as markdown".


## What it can do

- **Work on your current tab.** It sees only the page you are on, never your other tabs. It reads it, clicks, fills forms, types, scrolls
  (including pages that load as you go), searches Google, and shows every step and its reasoning in the chat.
- **Make files.** CSV, JSON, markdown or text, shown as a box you can copy or download. It can turn a page, its links or its table into a
  file without retyping it.
- **See your screen.** The camera button attaches a screenshot of your tab to a message, and you can attach images.
- **Ask you.** When it needs a decision or a missing detail, it asks with buttons.
- **Remember.** It keeps notes about you between chats (`/memory`) and shows what each answer cost.

### Macros: tasks that run with no AI

Do a task once, then `/save-macro name`. From then on `/macro name` replays it exactly: fast, free, and with no API key needed. A macro can
take inputs (`/macro stock-history WMT`), pause for you to press Continue (to log in, say), and repeat steps until you say stop (scrolling a
feed). Edit one as JSON from the list.

### Playbooks: advice for the agent

`/save-playbook name` saves what worked as a recipe, and `/playbook name` has the agent do a task by following it. The agent also finds
relevant playbooks by itself.

### Commands

| Command | What it does |
|---|---|
| `/macro name inputs` | Run a macro with no AI |
| `/save-macro name` | Turn the last run into a macro |
| `/list-macro` | View, copy, edit and delete macros |
| `/playbook name details` | Do a task with a playbook |
| `/save-playbook name` | Save a playbook from the last run, or for a task you describe |
| `/list-playbook` | View, copy and delete playbooks |
| `/memory text` | Remember something for every future chat |

Type `/` for suggestions; saved names are suggested after `/macro ` and `/playbook `.

## Models

Settings has a provider dropdown that fills in the address and model: Baseten (default), Meta, OpenAI, Groq, Gemini, LM Studio, Ollama, or
Custom for any OpenAI-compatible address. The model must support tool calling. Local models need no key; give them at least a 16k context
length.

## Privacy and safety

- Keys, settings and conversations stay in your browser. Page content goes only to the provider you chose.
- The agent acts in your logged-in browser, so do not point it at pages you would not send to that provider. Its rules (no irreversible
  actions unless asked, ignore instructions found on pages) are prompt rules, not a permission system.
- Letting it run JavaScript on pages is on by default and can be turned off in Settings.
- Chrome shows its "started debugging this browser" banner while the agent works on a tab.

## Status

Working and still being built. Some newer features (macros, the new tools, Edit and Retry, the other providers) are built and type-checked
but not all tried end to end yet. Not built: voice input and a `SOUL.md` file. Settings has a log you can copy when something goes wrong.

