# Repo-Masters: Agent Memory Vault & Repository Registry

Centralized offsite registry of all repositories, frameworks, and architecture standards stored across agent sessions. Repositories are strictly partitioned into **Global** (universal standards) and **Project-Scoped** (isolated to specific projects) to prevent context pollution and memory leaks across unrelated codebases.

---

## 1. Global Repositories (Universal across all projects)

### Unslop
- **Scope**: `Global` (All projects)
- **Repository**: https://github.com/OPSHARP/unslop
- **Local Location**: `~/.gemini/skills/unslop`
- **Category**: Writing Standard & Agent Skill
- **Directives**:
  - Direct, active voice; single-idea sentences.
  - Zero conversational filler, sycophancy, or AI clichés (*delve*, *tapestry*, *testament*, *landscape*, *crucial*, *furthermore*, *pivotal*, *robust*, *foster*, *leverage*).
  - Exact preservation of code, parameters, URLs, and operational constraints.

### Repo-Masters
- **Scope**: `Global` (All projects)
- **Repository**: https://github.com/PranavSharma1008/Repo-Masters.git
- **Local Location**: `~/.gemini/references/Repo-Masters`
- **Category**: Central Memory Vault & Registry
- **Directives**:
  - Stores all registered repositories and core instructions offsite on GitHub.
  - Keeps agent memory resilient against local data loss or session resets.
  - Automatically commits and pushes new entries whenever added.

---

## 2. Project-Scoped Repositories: BlackyAgent

> [!NOTE]
> The following repositories are scoped strictly to **BlackyAgent** (`/Users/pranavsharma/Documents/Projects /Pending /BlackyAgent`). They are ignored when working on unrelated workspaces (e.g. Blood Ocean, web apps, or backend services).

### Blacky / BlackyAgent (Core Project)
- **Scope**: `BlackyAgent`
- **Repository**: https://github.com/PranavSharma1008/Blacky.git
- **Local Location**: `/Users/pranavsharma/Documents/Projects /Pending /BlackyAgent`
- **Category**: Desktop Assistant (macOS Native)
- **Directives**: Dedicated strictly to macOS. Option/Fn push-to-talk voice, local Ollama function calling, deterministic fast-path routing, and compact floating companion window.

### Browser-Use
- **Scope**: `BlackyAgent` (Web Automation Subsystem)
- **Repository**: https://github.com/browser-use/browser-use
- **Local Location**: `~/.gemini/references/browser-use`
- **Category**: Web Automation Framework
- **Directives**: Primary benchmark for autonomous web interactions, DOM pruning, coordinate clicking, and visual element grounding.

### Microsoft OmniParser
- **Scope**: `BlackyAgent` (Screen Grounding & Vision Automation)
- **Repository**: https://github.com/microsoft/OmniParser
- **Category**: GUI Screen Parser & Grounding Engine
- **Directives**: Parses desktop/UI screenshots into structured bounding boxes with semantic icon and text labels. Eliminates manual OCR coordinate guessing for WhatsApp and web desktop automation.

### ShowLab ShowUI
- **Scope**: `BlackyAgent` (Screen Grounding & Vision Automation)
- **Repository**: https://github.com/ShowLab/ShowUI
- **Category**: Desktop GUI Vision-Language Model
- **Directives**: Vision-language architecture trained specifically for desktop UI grounding and click navigation, optimized for desktop layouts.

### Faster-Whisper
- **Scope**: `BlackyAgent` (Local Voice - Speech-to-Text)
- **Repository**: https://github.com/SYSTRAN/faster-whisper
- **Category**: Fast Local STT (CTranslate2)
- **Directives**: 100% local, low-latency Speech-to-Text on Apple Silicon M2. Replaces cloud speech APIs and handles Indian English accents accurately.

### RealtimeSTT
- **Scope**: `BlackyAgent` (Local Voice - Speech-to-Text)
- **Repository**: https://github.com/KoljaB/RealtimeSTT
- **Category**: Real-time STT with Voice Activity Detection (VAD)
- **Directives**: Zero-delay push-to-talk audio streaming for Fn/Option walkie-talkie mode with automatic voice activity boundary detection.

### Piper
- **Scope**: `BlackyAgent` (Local Voice - Text-to-Speech)
- **Repository**: https://github.com/rhasspy/piper
- **Category**: Fast Local Neural TTS Engine
- **Directives**: High-performance local neural speech synthesis with natural voices running in real time on Mac CPU/GPU with near-zero latency.

### Smolagents
- **Scope**: `BlackyAgent` (Agent Runtime & Tool Execution)
- **Repository**: https://github.com/huggingface/smolagents
- **Category**: Minimalist Code-as-Action Agent Framework
- **Directives**: Replaces heavy JSON tool schemas with direct Python tool execution loops, preventing small local models (`qwen3.5:4b`) from hallucinating or choking on context windows.

### Anthropic Computer-Use Demo
- **Scope**: `BlackyAgent` (Desktop Action Loops)
- **Repository**: https://github.com/anthropics/anthropic-quickstarts/tree/main/computer-use-demo
- **Category**: OS Action Loop & Safety Reference
- **Directives**: Reference patterns for coordinate clicking, keyboard typing, screenshot capture loops, click recovery, and safety gating.

### Rumps
- **Scope**: `BlackyAgent` (macOS Native Controls)
- **Repository**: https://github.com/jpscaletti/rumps
- **Category**: macOS Status Bar Python Wrapper (Cocoa NSStatusBar)
- **Directives**: Clean Python patterns for macOS Menu Bar status icons, menu actions, floating companions, and background daemons.

### Mem0
- **Scope**: `BlackyAgent` (Persistent Memory Layer)
- **Repository**: https://github.com/mem0ai/mem0
- **Category**: Adaptive Long-Term Memory Engine
- **Directives**: Memory layer extracting user preferences, past session outcomes, and facts across days with local SQLite/embeddings.

### Letta
- **Scope**: `BlackyAgent` (Hierarchical Memory Architecture)
- **Repository**: https://github.com/letta-ai/letta
- **Category**: OS-Style Memory & Context Management
- **Directives**: Hierarchical memory management partitioning working context (RAM) from archival storage (Disk) to prevent small context overflow.

---

## 3. Project-Scoped Repositories: BloodOcean

> [!IMPORTANT]
> **Strict Domain Isolation**: When active in **BloodOcean** (or any non-agent / database / web app project), all BlackyAgent, GUI automation, voice, and agent action loop repositories are **strictly deactivated and forbidden**. Only repositories relevant to BloodOcean's domain (e.g. DBMS, database schemas, web endpoints) are to be used.

*(No external repositories registered for BloodOcean yet. Repositories added for BloodOcean will be tagged with `Scope: BloodOcean`).*

---

## 4. Automated Sync Protocol

Whenever a new repository is added to memory:
1. Append the repository entry with its explicit `Scope` (`Global` or specific project name) to this file (`README.md`).
2. Commit and push the changes:
   ```bash
   git -C ~/.gemini/references/Repo-Masters add README.md
   git -C ~/.gemini/references/Repo-Masters commit -m "Add <repo-name> (Scope: <scope>) to memory vault"
   git -C ~/.gemini/references/Repo-Masters push origin main
   ```
3. Update the relevant project's `GEMINI.md` or `MEMORY.md` if scoped, or `~/.gemini/GEMINI.md` if global.

---

## 4. Disaster Recovery Protocol

If agent memory or session state is reset:
1. Pull the latest state:
   ```bash
   git -C ~/.gemini/references/Repo-Masters pull origin main
   ```
2. Read `~/.gemini/references/Repo-Masters/README.md`.
3. Check the scope of each repository:
   - Restore `Global` entries into `~/.gemini/GEMINI.md`.
   - Restore `Project-Scoped` entries only into their respective project folders.
