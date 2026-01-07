# Plancute – Specs-Driven Product Planning Template

Plancute is a **project template for structured, agent-assisted product planning**.  
It is designed to help teams move from ideas to execution **without skipping critical thinking steps**.

This repository is intentionally opinionated:  
it enforces a **specification-first workflow** that separates intent, decisions, and execution.

---

## What this template is for

Use this template when you want to:

- Plan a new product or feature systematically
- Avoid premature design or implementation
- Work effectively with AI agents (e.g. Codex) without losing structure
- Create clear specifications before breaking work into tasks
- Maintain alignment between vision, scope, and execution

This is especially useful for:
- Product discovery and early planning
- Agentic or AI-assisted product management
- Teams that want repeatable, high-signal planning artifacts

---

## Core working principles

This project follows a **phased approach** to product work:

1. **Planning before designing**  
   Clarify *what* you are building and *why* before deciding *how* it looks or works.

2. **Separating problems from solutions**  
   Requirements and intent are captured independently of UI, code, or tasks.

3. **Decisions before execution**  
   Trade-offs and priorities are made explicit before work begins.

4. **Execution as the final step**  
   Implementation happens only after shared understanding exists.

This structure reduces rework, improves decision quality, and keeps execution aligned with intent.

---

## How work progresses in this repository

Work flows through a small number of clearly defined steps:

1. **Plan the product**
   - Define the problem, goals, constraints, and success criteria
   - Establish shared understanding

2. **Shape and write specifications**
   - Turn intent into explicit requirements
   - Document assumptions and boundaries

3. **Create executable tasks**
   - Break approved specifications into concrete work items

4. **Execute**
   - Design, implement, or orchestrate work based on the agreed spec

Each step produces artifacts that become the input for the next step.

Skipping steps is intentionally discouraged.

---

## Working with AI agents

This repository is designed to work well with AI coding and planning agents (such as Codex).

To keep outputs high-quality and predictable:

- Agents are guided to follow the same phased workflow as humans
- Ad-hoc execution (e.g. “just make a UI”) is intentionally blocked
- When a shortcut is attempted, the agent explains the workflow and points to the correct next step

This ensures AI assistance strengthens thinking instead of bypassing it.

---

## Repository structure (high level)

```
/
├─ agent-os/
│  ├─ commands/        # Step-by-step workflow commands
│  └─ specs/           # Product and feature specifications
│
├─ AGENTS.md           # Rules and guidance for agent behavior
└─ README.md           # You are here
```

You do not need to understand all of this on day one.  
The workflow is designed to teach itself through use.

---

## How to start a new project

1. Click **“Use this template”** on GitHub
2. Clone the new repository
3. Start with the planning step
4. Follow the workflow step by step

If you are using an AI agent, it will guide you to the correct next action.

---

## Philosophy

This template is based on a simple belief:

> **Clarity before speed leads to faster outcomes overall.**

By slowing down at the right moments, teams move faster where it matters.

---

## License

Use this template freely for personal or commercial projects.  
Adapt it to your needs, but keep the core principle intact:  
**think before you build**.