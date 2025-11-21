# BMAD LifeOps Personal Operating System

**Version 1.2 — Spec-Driven, Multi-Agent, Idea Verification & Action-First**

## Overview

BMAD LifeOps is an orchestrated **multi-agent Life Operating System** designed to turn your goals and ideas into verified specs, structured plans, and concrete actions. It treats you as the **CTO of Your Life**, providing a structured framework to manage your personal and professional growth.

## The BMAD Method

The system operates on the **BMAD** lifecycle:

*   **B – Brainstorm**: Expand possibilities, explore options and perspectives.
*   **M – Map**: Turn ideas into structured plans, strategies, and roadmaps.
*   **A – Act**: Execute plans, manage tasks, and track actions.
*   **D – Debrief**: Reflect, learn, and adjust based on outcomes.

## The Agents

The system implements five internal agents to handle different aspects of the lifecycle:

1.  **`[O]` Orchestrator**: Coordinates agents, tracks context, and manages the lifecycle.
2.  **`[B]` Brainstormer**: Explores options and asks probing questions.
3.  **`[M]` Mapper**: Structures goals and verifies specs.
4.  **`[A]` Activator**: Translates plans into actionable tasks and schedules.
5.  **`[D]` Debriefer**: Runs reviews and extracts insights.

## Getting Started

To use this system, load the `1.1/00_Master.txt` prompt into your LLM context. The Orchestrator `[O]` will initialize the session and guide you through the process.

### Key Commands

*   `/today`: Design today’s operating plan.
*   `/review today`: Short daily retrospective.
*   `/review week`: Weekly review and reset.
*   `/crisis`: Triage mode for when you are overloaded.
*   `*where`: Show current BMAD phase and context.
*   `*reset`: Clear current topic and start fresh.

## Idea Verification Mode

For any new idea or initiative, the system defaults to **Idea Verification Mode**:
1.  **Clarify & Mirror** (`[B]`): Understand the intent and constraints.
2.  **Verify & Structure** (`[M]`): Check feasibility and draft a v0.1 spec.
3.  **Action Needed** (`[A]`): Break down into concrete `[NOW]`, `[NEXT]`, and `[LATER]` actions.
