# VIR (Verifică · Investighează · Rezolvă)

> Autonomous Tri-Phase Debug & Fix Protocol for AI Coding Agents (Google Antigravity, Claude Code, Cursor, Windsurf).

---

## 🎯 What is VIR?

VIR is a strict, evidence-driven engineering protocol designed to prevent AI agents from "blind fixing" bugs by guessing. It enforces a strict rule: **Never modify code before finding the root cause.**

```text
Phase 1: VERIFICĂ         Phase 2: INVESTIGHEAZĂ         Phase 3: REZOLVĂ
[Reproduce & Evidence] ──> [Root Cause / NO EDITING] ──> [Surgical Fix & Regression Check]
```

---

## 🚀 The 3 Phases

### 1. Phase 1: VERIFICĂ (Verify & Reproduce)
- Locate failing tests, stack traces, or error logs.
- Run the failing command or write a minimal reproduction script.
- **Gate 1:** If the defect cannot be reproduced locally, **STOP**. Do not modify any code based on assumptions.

### 2. Phase 2: INVESTIGHEAZĂ (Root-Cause Analysis)
- Trace execution flow backwards from the failure point.
- **STRICT RULE: NO CODE EDITING IN THIS PHASE.**
- Isolate whether it is a state drift, race condition, missing boundary check, or environment mismatch.
- Document exact file and line: `path/to/file:line`.

### 3. Phase 3: REZOLVĂ (Surgical Patch & Verification)
- Apply the minimal possible patch.
- Re-run Phase 1 reproduction to prove the bug is gone.
- Run the full test suite to ensure zero regressions.

---

## 📦 Installation

### Global (All projects)
* **Google Antigravity**: Copy to `~/.gemini/config/skills/vir/`
* **Claude Code**: Copy to `~/.claude/skills/vir/`

### Project-Level
* **Antigravity**: `.agents/skills/vir/`
* **Claude Code**: `.claude/skills/vir/`

---

## 💡 Usage

```text
/vir auth token expiration issue in auth.service.ts
```
*(or simply in natural language)*:
```text
Apply the VIR protocol to fix the failing test in checkout.spec.ts
```

---

## 📄 License

MIT
