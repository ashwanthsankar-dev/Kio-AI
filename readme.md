Kio A1. 
**Prompt Ingestion**: Receives developer task prompts from command-line arguments.
2. **Context Enrichment**: Routes the prompt through OpenRouter (`openrouter/free`) to inject team standards, environment specifications, and architectural constraints.
3. **`CLAUDE.md` Sync**: Automatically writes/updates `CLAUDE.md` in the working directory to enforce native context adherence for Claude Code.
4. **Automated Handoff**: Spawns the official Claude Code CLI (`claude -p`) with the fully enriched context.

---

## ✨ Features

- **Automated Personalization**: Eliminates manual boilerplate prompt engineering.
- **Dynamic Context Injection**: Keeps local workspace `CLAUDE.md` files synchronized with live task state.
- **Dry-Run Inspection (`-d`)**: Preview enriched prompts and inspect `CLAUDE.md` changes before launching execution.
- **Defensive Configuration**: Fail-safe JSON loaders (`settings.json`, `team_profiles.json`) prevent key errors and handle API fallbacks smoothly.
- **Zero-Dependency Core**: Powered by Python standard libraries + `requests`.

---

## 📋 Prerequisites

- **Python**: `3.10+` (3.12 recommended)
- **Node.js & Claude Code CLI**:
  ```bash
  npm install -g @anthropic-ai/claude-code