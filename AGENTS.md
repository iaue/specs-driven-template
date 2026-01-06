Agent OS Directives (Codex)

1) Non-negotiable rule

This repository follows Agent OS. All agent work MUST be executed via Agent OS command files in agent-os/commands/ and MUST produce/modify Agent OS artifacts in the expected locations.

If a request is not clearly tied to an Agent OS command, the agent MUST stop and ask which Agent OS command to run next.

2) Canonical workflow (Agent OS)

Agents MUST follow the Agent OS workflow:

Run once
	1.	plan-product

Repeatable per feature/spec
	2.	shape-spec (optional if requirements are already clear)
	3.	write-spec
	4.	create-tasks
	5.	implement-tasks OR orchestrate-tasks (choose one per spec)

This ordering MUST NOT be bypassed.  ￼

3) Codex invocation protocol (required)

In Codex, agents MUST run Agent OS commands by referencing the command file with @ and instructing Codex to run it, e.g.:
	•	@agent-os/commands/write-spec/write-spec.md run this  ￼

If a command supports numbered step files, the agent MAY run the steps sequentially for reliability (preferred when outputs are complex or high-stakes).  ￼

4) Phase gating and refusal policy (strict)

4.1 Preconditions

The agent MUST verify prerequisites before proceeding:
	•	write-spec requires either:
	•	completed shape-spec, or
	•	explicitly confirmed “requirements are already clear; skip shape-spec”
	•	create-tasks requires a completed spec (from write-spec)
	•	implement-tasks / orchestrate-tasks require tasks created from create-tasks
	•	plan-product should be completed once before feature work whenever feasible

4.2 Mandatory refusal behavior

If asked to do work that bypasses the workflow (examples: “just implement this,” “write code now,” “create tasks without a spec”), the agent MUST respond only:

Agent OS violation: This request bypasses required phase(s).
Required next command: @agent-os/commands/<next-command>/<next-command>.md run this

No partial compliance. No “quick draft anyway.”

5) Artifact rules (source of truth)

Agents MUST treat Agent OS artifacts as authoritative.

5.1 Where specs live

write-spec produces a spec document under:
	•	agent-os/specs/<this-spec>/spec.md  ￼

Agents MUST read and follow the current spec before generating tasks or implementing.

5.2 No silent scope changes

If implementation reveals missing requirements, ambiguous behavior, or new edge cases:
	•	the agent MUST stop implementation
	•	return to shape-spec or write-spec to update the spec
	•	then regenerate tasks if needed

6) Output discipline

For any response, the agent MUST:
	1.	State which Agent OS command it is executing (or recommending).
	2.	Produce only outputs appropriate to that command.
	3.	Reference the relevant spec/task artifacts when continuing work.

Agents MUST NOT mix “spec writing” and “implementation” in one step unless the command explicitly instructs it.

7) Implementation mode selection

For each spec, pick exactly one:
	•	implement-tasks: direct implementation with the main agent
	•	orchestrate-tasks: advanced orchestration / delegation (typically for complex work)

Do not use both for the same spec.  ￼

8) If the user gives an ad-hoc prompt

When the user asks something ad-hoc (not a command), the agent MUST respond with:
	1.	the recommended next Agent OS command (with the Codex @... run this form), and
	2.	the minimum clarifying question(s) needed to run that command correctly.