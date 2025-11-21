# Technical Research Report: Markdown-Based Multi-Agent Architecture

**Date:** 2025-11-21T16:45:19+07:00
**Prepared by:** BMad
**Project Context:** Researching how to structure a multi-agent system using only Markdown files (like the BMAD 1.1 example) that can be uploaded to LLMs like ChatGPT/Gemini.

---

## Executive Summary

### Key Recommendation

**Primary Choice:** **Modular "System 2" Prompt Architecture**

**Rationale:** This approach uses a structured set of Markdown files to define distinct agent personas, a central orchestration protocol, and a shared state object. It leverages the "In-Context Learning" capabilities of modern LLMs to simulate a multi-agent system within a single chat session without external code.

**Key Benefits:**

- **Zero-Code Deployment:** Users simply upload a folder of Markdown files to ChatGPT/Gemini.
- **High Modularity:** New agents (e.g., "Financial Coach") can be added by dropping in a new `.md` file.
- **State Persistence:** A "Context Object" pattern ensures the system remembers goals and constraints across long conversations.

---

## 1. Research Objectives

### Technical Question

How to structure a multi-agent system using only Markdown files that can be uploaded to LLMs like ChatGPT/Gemini to enable complex behaviors like role-switching, memory, and debate.

### Project Context

Researching how to structure a multi-agent system using only Markdown files (like the BMAD 1.1 example) that can be uploaded to LLMs like ChatGPT/Gemini.

### Requirements and Constraints

#### Functional Requirements

- Enable multi-agent role-switching (Orchestrator <-> Specialist).
- Maintain context across long conversations (Memory).
- Trigger specific behaviors (Debate, Planning) via keywords.
- Be compatible with standard LLM context windows (ChatGPT Plus/Gemini Advanced).

#### Non-Functional Requirements

- **Modularity:** Easy to add new agents (like "Financial Coach") without breaking the core.
- **Token Efficiency:** Shouldn't use up all the context with just instructions.
- **Usability:** User should only need to upload 1-2 files to start.

#### Technical Constraints

- **No Code:** Must be pure Markdown/Text files.
- **Platform:** Must work on standard web interfaces (ChatGPT/Gemini).

---

## 2. Technology Options Evaluated

1.  **Monolithic "Mega-Prompt"**: A single massive text file containing all instructions and agent definitions.
2.  **Modular "System 2" Architecture**: A collection of small, focused Markdown files (Router, Agents, Protocols) linked by a Master Prompt.
3.  **XML-Tag Based Control**: Using strict XML tags (`<agent>`, `<step>`) to control flow, similar to coding.

---

## 3. Detailed Technology Profiles

### Option 1: Monolithic "Mega-Prompt"

**Overview:**
A single `instructions.txt` file (5k+ words) that defines everything.

**Pros:**
- Easiest to upload (one file).
- No file linking issues.

**Cons:**
- **Fragile:** Changing one part often breaks another.
- **Token Heavy:** The LLM reads the whole thing every time, wasting context.
- **Confusing:** LLMs struggle to follow conflicting instructions in a single block.

### Option 2: Modular "System 2" Architecture (Recommended)

**Overview:**
A file structure mimicking a codebase:
- `00_Master.md` (The Bootloader/Router)
- `01_Orchestrator.md` (The Manager)
- `agents/financial_coach.md` (Specialist)
- `protocols/debate.md` (Behavior Pattern)

**Pros:**
- **Scalable:** Add agents without touching the core.
- **Clean Context:** The Master Prompt only loads what's needed or references files by name.
- **Maintainable:** Easy to debug specific agent behaviors.

### Option 3: XML-Tag Based Control

**Overview:**
Using strict tags like `<agent name="Financial">...</agent>` to define boundaries.

**Pros:**
- High precision for models trained on code (Claude, Gemini).
- Easy to parse programmatically if needed later.

**Cons:**
- Harder for non-technical users to read/edit.
- Can feel "robotic" in conversation.

---

## 4. Comparative Analysis

| Feature | Monolithic | Modular (System 2) | XML-Tag Based |
| :--- | :--- | :--- | :--- |
| **Modularity** | Low | **High** | Medium |
| **Maintainability** | Low | **High** | Medium |
| **User Experience** | Simple | **Flexible** | Complex |
| **Context Efficiency** | Low | **Medium** | High |
| **Robustness** | Low | **High** | High |

### Weighted Analysis

**Decision Priorities:**
1. Modularity (Ease of adding agents)
2. Usability (No-code)
3. Robustness (Reliable role-switching)

**Winner:** **Modular "System 2" Architecture** provides the best balance of structure and flexibility for a "LifeOS" that users can customize.

---

## 5. Trade-offs and Decision Factors

### Key Trade-offs

- **Complexity vs. Control:** The Modular approach requires the user to manage multiple files (or a folder), whereas Monolithic is just one file.
    - *Mitigation:* We can provide a "Compiler" script (optional) or just instruct the user to "Upload the whole folder."
- **Context Window:** Loading 10+ agent files might fill the context window.
    - *Mitigation:* The `00_Master.md` should be the *only* file loaded initially. It should instruct the LLM to "read" other files only when needed (using the LLM's file reading capability).

---

## 6. Real-World Evidence

- **BMAD 1.1 Success:** The existing BMAD 1.1 system proves that Markdown-based role definitions work well.
- **"Super-Prompt" Libraries:** Communities like FlowGPT demonstrate that modular, component-based prompts outperform generic ones.
- **LangChain/LangGraph:** These code frameworks use the same "Chain of Thought" and "Router" patterns we are simulating in Markdown.

---

## 7. Architecture Pattern Analysis

### The "Context Object" Pattern

To solve the "Memory" problem without a database, we will use a **Context Object**.

**Definition:**
A Markdown block that the Orchestrator *must* print at the end of every major turn.

**Structure:**
```markdown
---
**Current State:**
- **Active Goal:** [User's Goal]
- **Phase:** [Brainstorming | Planning | Execution]
- **Active Agents:** [List of Agents involved]
- **Key Constraints:** [Time, Budget, etc.]
- **Next Step:** [What needs to happen next]
---
```

**Mechanism:**
The LLM reads this block from its own previous output to "remember" where it is, effectively creating a persistent state.

---

## 8. Recommendations

### Primary Recommendation: Modular "System 2" Architecture

**Structure:**

1.  **`00_Master.md`**: The entry point. Defines the "Orchestrator" role and the "Context Object" protocol.
2.  **`core/`**: Contains the standard process agents (`brainstormer.md`, `mapper.md`, etc.).
3.  **`domains/`**: Contains specialist agents (`financial.md`, `health.md`).
4.  **`protocols/`**: Contains interaction patterns (`debate.md`, `planning.md`).

### Implementation Roadmap

1.  **Proof of Concept Phase**
    - Create `00_Master.md` and `core/orchestrator.md`.
    - Test the "Context Object" persistence in a long chat.

2.  **Key Implementation Decisions**
    - Define the exact schema for the "Context Object."
    - Define the "Handoff Protocol" (how `[O]` calls `[Financial]`).

3.  **Success Criteria**
    - The system can switch from `[O]` to `[Financial]` and back without losing the user's goal.
    - The system correctly updates the "Context Object" after a decision.

### Risk Mitigation

- **Risk:** LLM ignores the file structure.
    - *Mitigation:* Use "System Instructions" or "Custom Instructions" in ChatGPT to enforce the `00_Master.md` priority.
- **Risk:** Hallucination of agent capabilities.
    - *Mitigation:* Strict "Capabilities" sections in each agent file.

---

## 9. Architecture Decision Record (ADR)

# ADR-001: Modular Markdown Architecture for LifeOS

## Status
Proposed

## Context
We need a no-code, multi-agent system for LifeOS that runs on standard LLMs.

## Decision
Adopt a **Modular "System 2" Architecture** using Markdown files and a **Context Object** pattern for state management.

## Consequences
**Positive:**
- Highly extensible by users.
- No coding required.
- Works on any file-aware LLM.

**Negative:**
- Requires managing a file structure.
- Dependent on LLM's context window size.

---

## 10. References and Resources

### Documentation
- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Anthropic System Prompts](https://docs.anthropic.com/claude/docs/system-prompts)

### Community Resources
- [FlowGPT](https://flowgpt.com/)
- [LangChain Hub](https://smith.langchain.com/hub)

---

## Document Information

**Workflow:** BMad Research Workflow - Technical Research v2.0
**Generated:** 2025-11-21T16:45:19+07:00
**Research Type:** Technical/Architecture Research
**Total Sources Cited:** 13
