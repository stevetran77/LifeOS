# Product Brief: LifeOS

**Date:** 2025-11-21T16:48:35+07:00
**Author:** BMad
**Context:** Product Kit (Open Source/Commercial)

---

## Executive Summary

LifeOS is a "No-Code" Personal Operating System Kit designed to run on standard LLMs (ChatGPT/Gemini). It transforms the user's relationship with AI from a simple chatbot into a "CEO vs. Staff" dynamic, where the user provides vision and a team of specialized AI agents (Orchestrator, Planner, Financial Coach, etc.) handles the execution, planning, and debate. It solves the problem of "planning fatigue" by automating the cognitive load of structuring goals and tasks.

---

## Core Vision

### Problem Statement

Users want to manage their lives better (goals, finance, health) but suffer from "Planning Fatigue." They don't know *how* to structure a plan, or they lack the energy to maintain it. Existing tools (Notion, To-Do apps) are just empty containers that require manual management. Standard chatbots give generic advice but lack context and continuity.

### Proposed Solution

A modular "Prompt Architecture" kit that users upload to their LLM. It instantly spins up a team of agents:
*   **[O] Orchestrator:** The Chief of Staff who manages the context and routes tasks.
*   **[M] Mapper:** The Strategist who turns vague goals into plans.
*   **Specialists:** Domain experts (Finance, Health) who provide specific advice.
*   **Debate Mode:** Agents argue trade-offs (e.g., "Save money" vs. "Enjoy life") to help the user decide.

### Key Differentiators

1.  **No-Code/Low-Friction:** No Python scripts or APIs to host. Just text files.
2.  **Multi-Agent Simulation:** Simulates a full team within a single chat session.
3.  **Debate Mode:** Explicitly surfaces trade-offs instead of giving one "safe" answer.
4.  **Context Persistence:** Uses a "Context Object" pattern to remember goals across sessions.

---

## Target Users

### Primary Users

**The "Overwhelmed Optimizer":**
*   Professionals, creators, or ambitious individuals who have many goals but feel scattered.
*   They likely already use ChatGPT and Notion but feel they aren't getting enough "strategic" help.
*   They want an "Executive Assistant" but can't afford a human one.

### User Journey

1.  **Setup:** User downloads the `LifeOS Kit` (folder of Markdown files).
2.  **Install:** User uploads the folder to ChatGPT/Gemini.
3.  **Initiate:** User types `/init`. The `[O] Orchestrator` introduces the team.
4.  **Goal Setting:** User says "I want to run a marathon."
5.  **Orchestration:** `[O]` calls the `[Health Coach]` to assess fitness and `[M] Mapper` to create a schedule.
6.  **Debate (Optional):** If the goal conflicts with budget, `[O]` triggers a debate between `[Financial Coach]` and `[Health Coach]`.
7.  **Execution:** The system updates the "Context Object" and gives daily briefings.

---

## MVP Scope

### Core Features

1.  **Agent Roster:** `[O] Orchestrator`, `[B] Brainstormer`, `[M] Mapper`, `[A] Activator`, `[D] Debriefer`.
2.  **Context Object Protocol:** The standard format for saving state at the end of messages.
3.  **Dynamic Routing:** The ability for `[O]` to "call" another agent based on user intent.
4.  **One Domain Specialist:** Start with **Financial Coach** or **Health Coach** as a demo.
5.  **Debate Mode:** A specific protocol where two agents discuss a topic for 3 turns before asking the user to decide.

### Out of Scope for MVP

*   Integration with external calendars (Google Calendar) - *Requires API/Code*.
*   Fully autonomous background tasks - *LLMs are reactive only*.
*   Mobile App - *We are building a Prompt Kit, not an App*.

---

## Market Context

**Competitors:**
*   **Notion Templates:** Static, require manual input.
*   **Sunsama/Motion:** Great for scheduling, but don't help with *strategy* or *coaching*.
*   **Standard ChatGPT:** Good for one-off questions, has no memory of "Life Strategy."

**Opportunity:**
There is a gap for a "Smart Layer" that sits on top of raw LLMs to give them structure without requiring the user to be a prompt engineer.

---

## Technical Preferences

*   **Format:** Pure Markdown (`.md`).
*   **Compatibility:** Optimized for models with large context windows (GPT-4o, Gemini 1.5 Pro).
*   **Distribution:** GitHub Repo or Zip file.

---

## Risks and Assumptions

*   **Risk:** LLM context limits might cut off the "Memory" after long chats.
*   **Risk:** Users might find uploading files "too technical."
*   **Assumption:** Users are willing to pay (or star) for a "Prompt Kit" rather than a SaaS app.

---

_This Product Brief captures the vision and requirements for LifeOS._
