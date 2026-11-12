# CLAUDE.md - Woodsbrow (working title)

## Project Overview
- **Engine:** Unity 6000.6.2f1 (Built-in render pipeline for now; nothing decided yet)
- **Game:** new project, design not defined yet. Everything we know lives in `Docs/README.md` and the docs it links.
- **Editor automation:** MCP for Unity (`com.coplaydev.unity-mcp` in `Packages/manifest.json`; server in `.mcp.json` → `uvx mcpforunityserver==10.1.2`)

## FIRST THING IN EVERY NEW CHAT (MANDATORY)
The user continues this project across several chats. Chats do not share memory: **the docs in this repo are the only memory**. Before doing any work in a new chat:
1. Read `Docs/HANDOFF.md` (where the last chat left off and what comes next).
2. Read `Docs/README.md` (the parent doc) and **every MD it links**, following the links down to the smallest mechanic doc. Do not skim: the mechanic docs hold the decisions.
3. Tell the user, in 3-6 lines of Spanish, what you understood: what the game is, what exists, what is in progress and what is next. Ask about anything that contradicts itself.
Only then start working.

## Working With the User
- Chat in **Spanish**. Code, comments, identifiers and in-game text in **English**. Everything under `Docs/` in **Spanish**.
- The user often dictates by voice: expect typos and read for intent. If an ambiguous word changes the work, ask; otherwise decide and say what you assumed.
- Short, plain answers: what you did, what the user should try, what is still open.
- **Commits and pushes only with the user's explicit OK** for that commit.
- Every file the user sends (image, PDF, reference) is saved into `Docs/Contexto/` and gets a row in `Docs/Contexto/README.md`. Attached PDFs are not kept by Claude Code, only their path: copy them right away.

## Documentation (MANDATORY)
The user wants **every thing we build described in an MD**, organised as a tree under one parent doc.
- **Parent doc:** `Docs/README.md`. It explains the game in short and links to every other MD. Nothing exists in the project without a link from it (directly or through a section index).
- **Section indexes:** `Docs/Mecanicas/README.md`, `Docs/Sistemas/README.md`, ... Each lists and links its child docs.
- **One MD per mechanic or system** (`Docs/Mecanicas/<Nombre>.md`): what it is and why, how it plays, controls, rules and numbers (tuning), the scripts/prefabs/scenes that implement it, its status, the user's feedback history, and an **Interacciones** section (which other mechanics/systems it touches, with links). Template: `Docs/Mecanicas/_PLANTILLA.md`.
- When something changes, update its MD **and** every MD that links to it or interacts with it (status lines, tables, indexes, Interacciones). After each advance, ask the user: **"¿Lo agrego a los MD afectados y nuevos?"** and list which ones.
- New folders or docs are added to the parent doc in the same session.
- `Docs/ESTADO.md` keeps the current state (what exists, what is in progress, next steps, open questions).

## Context limit and handoff (MANDATORY)
- Watch the conversation length. **When roughly 75-80 % of the context window is used** (or the conversation is very long and close to being summarized), **warn the user in Spanish** that the chat is running out of space.
- With that warning, update `Docs/HANDOFF.md` (the full handoff: state, what was done in this chat, decisions, open questions, exact next step, which MDs to read) plus `Docs/ESTADO.md` and every MD affected, then ask for the OK to commit + push so the next chat (on any computer) sees it.
- Give the user the first message to paste in the new chat: *"Lee CLAUDE.md, después Docs/HANDOFF.md y todos los MD que enlaza Docs/README.md, y dime qué entendiste del proyecto antes de seguir."*

## Unity Editor Rules
- **Never compile while the editor is in Play mode** (a domain reload in Play breaks the running test). If the user writes while in Play, stop Play, then apply the change.
- After writing scripts, check the console for compile errors through MCP before using the new types.
- Physics forces go in `FixedUpdate`, never `Update`.
- Changing a code default does not update existing prefabs/scenes: re-save them and say so.
- Nothing may flash faster than ~2 Hz (photosensitivity).

## Coding Conventions
- C# naming: PascalCase public members, camelCase locals, private fields `_camelCase`.
- `[SerializeField] private` for inspector references, never public fields.
- One class per file, file name = class name. Namespaces `Woodsbrow.<System>`.
- New Input System only (`Mouse.current` / `Keyboard.current`) once it is installed.

## Project Structure
```
Assets/                 # empty for now
Packages/manifest.json  # includes com.coplaydev.unity-mcp
Docs/
  README.md             # PARENT DOC: links to everything
  HANDOFF.md            # read first in every new chat
  ESTADO.md             # current state, next steps, open questions
  Mecanicas/            # README index + one MD per mechanic (+ _PLANTILLA.md)
  Contexto/             # everything the user sends (images, PDFs)
.mcp.json               # MCP for Unity server config
```
