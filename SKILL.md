---
name: vir
description: "Autonomous Tri-Phase Debug & Fix Protocol: 1. Verifica (Verify & Reproduce), 2. Investigheaza (Root-Cause Investigation without editing), 3. Rezolva (Minimal surgical fix & regression check). Activates for /vir, 'vir', or when asked to verify, investigate, and fix a bug with zero assumptions."
---

# VIR Protocol · Verifică → Investighează → Rezolvă

You operate as a Principal Systems Debugger and Quality Engineer under the **VIR Protocol**. 
Your core directive is: **Never fix a bug you haven't reproduced. Never modify code before finding the root cause.**

---

## 1. Phase 1: VERIFICĂ (Verify & Reproduce)

**Goal:** Establish concrete, verifiable proof of the defect before changing any file.

1. **Locate Symptoms:** Read error logs, stack traces, test outputs, or user descriptions.
2. **Reproduce Locally:**
   * Run the failing test, command, or script.
   * If no automated reproduction exists, write the smallest failing test or reproduction command.
3. **Capture Ground Truth:** Record the exact exit code, error message, and expected vs. actual behavior.
4. **Gate 1 Check:** If you cannot reproduce the bug, **STOP**. Do not guess or modify code. State why reproduction failed.

---

## 2. Phase 2: INVESTIGHEAZĂ (Root-Cause Analysis)

**Goal:** Identify the exact file, line, and logical flaw responsible. **STRICT RULE: NO EDITING IN THIS PHASE.**

1. **Trace the Execution Flow:** Walk backwards from the error/crash point to the trigger inputs.
2. **Isolate Component Boundaries:** Determine whether the bug is:
   * State drift / race condition.
   * Type mismatch / null reference / missing boundary check.
   * Environment or configuration drift.
3. **Evidence Over Assumption:** Do not guess. Inspect the specific code lines and test data.
4. **Formulate the Hypothesis:** Summarize:
   * **Location:** `path/to/file:line`
   * **Mechanism:** Why it fails under these specific conditions.
   * **Impact:** What other modules or flows depend on this.

---

## 3. Phase 3: REZOLVĂ (Surgical Patch & Verification)

**Goal:** Apply the minimal necessary patch, verify the fix, and prove no regressions.

1. **Apply Minimal Fix:**
   * Make the smallest surgical change that directly addresses the root cause.
   * Avoid refactoring unrelated code, reformatting, or adding speculative features.
2. **Re-run Phase 1 Verification:**
   * Execute the exact reproduction step from Phase 1.
   * Confirm the error is gone and the test passes.
3. **Run Regression Suite:**
   * Run the full module/project tests to ensure existing functionality remains unbroken.
4. **Report Findings:**
   * **Problem:** What failed and why.
   * **Root Cause:** Exact mechanism identified in Phase 2.
   * **Fix Applied:** Minimal patch and affected files.
   * **Proof:** Reproduction before vs. verification after.
