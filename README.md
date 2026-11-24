# Repo-Masters: Agent Memory Vault & Repository Registry

Centralized offsite registry of all repositories, frameworks, and architecture standards stored across agent sessions. If local session or agent memory is ever lost, reconstruct knowledge from this registry.

---

## 1. Registry of Tracked Repositories

### Unslop
- **Repository**: https://github.com/OPSHARP/unslop
- **Local Location**: `~/.gemini/skills/unslop`
- **Category**: Writing Standard & Agent Skill
- **Directives**:
  - Direct, active voice; single-idea sentences.
  - Zero conversational filler, sycophancy, or AI clichés (*delve*, *tapestry*, *testament*, *landscape*, *crucial*, *furthermore*, *pivotal*, *robust*, *foster*, *leverage*).
  - Exact preservation of code, parameters, URLs, and operational constraints.

### Browser-Use
- **Repository**: https://github.com/browser-use/browser-use
- **Local Location**: `~/.gemini/references/browser-use`
- **Category**: Web Automation Framework
- **Directives**:
  - Primary architectural reference for autonomous web agents.
  - DOM tree pruning, coordinate clicking, visual element grounding, and resilient tab management.

### Blacky / BlackyAgent
- **Repository**: https://github.com/PranavSharma1008/Blacky.git
- **Local Location**: `/Users/pranavsharma/Documents/Projects /Pending /BlackyAgent`
- **Category**: Desktop Assistant (macOS Native)
- **Directives**:
  - Dedicated strictly to macOS (no Windows/Linux branches).
  - Push-to-talk voice interaction (Fn/Option walkie-talkie).
  - Local Ollama function calling with deterministic fast-path execution.
  - Screen analysis companion and WhatsApp Desktop native automation.

### Repo-Masters
- **Repository**: https://github.com/PranavSharma1008/Repo-Masters.git
- **Local Location**: `~/.gemini/references/Repo-Masters`
- **Category**: Central Memory Vault
- **Directives**:
  - Stores all registered repositories and core instructions offsite on GitHub.
  - Keeps agent memory resilient against local data loss or session resets.

### AgentMemory
- **Repository**: https://github.com/rohitg00/agentmemory.git
- **Local Location**: `~/.gemini/references/agentmemory`
- **Category**: Persistent Memory & MCP Runtime
- **Directives**:
  - 4-tier memory consolidation (working, episodic, semantic, procedural).
  - Hybrid BM25, dense vector search, and knowledge graph traversal.
  - Native Antigravity skills: `remember`, `recall`, `lesson`, `forget`, `handoff`, `recap`, `memory-discipline`.

### Scientific Agent Skills
- **Repository**: https://github.com/K-Dense-AI/scientific-agent-skills.git
- **Local Location**: `~/.gemini/references/scientific-agent-skills`
- **Category**: AI Scientist & Computational Research
- **Directives**:
  - 170+ domain skills spanning genomics, single-cell RNA-seq, cheminformatics (RDKit, docking), clinical modeling (BIDS), and hypothesis trees (Arbor).
  - Native Antigravity skill: `scientific-skills`.

### Diagram Design
- **Repository**: https://github.com/cathrynlavery/diagram-design.git
- **Local Location**: `~/.gemini/references/diagram-design`
- **Category**: Technical Diagramming & Visual Architecture
- **Directives**:
  - Editorial design system for 52 diagram types (system architecture, sequence, ER diagrams, Sankey, axonometric).
  - Clean HTML/SVG outputs with sharp 1px borders, 4px grid, and no drop-shadow boilerplate.
  - Native Antigravity skill: `diagram-design`.

### Anthropic Cybersecurity Skills
- **Repository**: https://github.com/mukul975/Anthropic-Cybersecurity-Skills.git
- **Local Location**: `~/.gemini/references/cybersecurity-skills`
- **Category**: Cybersecurity & Threat Operations
- **Directives**:
  - 818+ senior cybersecurity skills mapped to MITRE ATT&CK, NIST CSF 2.0, D3FEND, and MITRE ATLAS.
  - Covers red teaming, DFIR, malware analysis, cloud hardening, and compliance.
  - Native Antigravity skill: `cybersecurity`.

### Awesome Harness Engineering
- **Repository**: https://github.com/ai-boost/awesome-harness-engineering.git
- **Local Location**: `~/.gemini/references/awesome-harness-engineering`
- **Category**: Agent Harness Engineering & Reliability
- **Directives**:
  - Architectural blueprints for production AI agent harnesses.
  - Maker-checker verification loops, eval-driven autonomy, and deterministic execution gates.
  - Native Antigravity skill: `harness-engineering`.

### OpenViking
- **Repository**: https://github.com/volcengine/OpenViking.git
- **Local Location**: `~/.gemini/references/openviking`
- **Category**: Agent Context Database & Virtual Filesystem
- **Directives**:
  - Virtual filesystem paradigm (`viking://`) organizing memory, skills, and sessions.
  - Self-evolving context with hierarchical retrieval.
  - Native Antigravity skills: `openviking-memory`, `openviking-skills`, `ov-experience-memory`, `ov-kanban`, `ov-resources`.


---

## 2. Automated Sync Protocol

Whenever the user instructs to add or store a new repository:
1. Append the repository details (Name, URL, Local Location, Category, Directives) to this file (`README.md`).
2. Run the Git sync commands:
   ```bash
   git -C ~/.gemini/references/Repo-Masters add README.md
   git -C ~/.gemini/references/Repo-Masters commit -m "Add <repo-name> to memory vault"
   git -C ~/.gemini/references/Repo-Masters push origin main
   ```
3. Update `~/.gemini/GEMINI.md` to ensure local runtime rules remain in sync.

---

## 3. Disaster Recovery Protocol

If agent memory or session state is reset:
1. Pull the latest state:
   ```bash
   git -C ~/.gemini/references/Repo-Masters pull origin main
   ```
2. Read `~/.gemini/references/Repo-Masters/README.md`.
3. Verify local clones exist at their designated paths; clone any missing repositories.
4. Restore global instructions into `~/.gemini/GEMINI.md`.
