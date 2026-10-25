# esr review: skills/planning-and-task-breakdown

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 3045f95a156dc71d7b5ac1e29ce795bb5cac2b71
- Date: 2026-10-25
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An instruction-only planning skill. It tells the agent to read a spec and
    the codebase without changing them, break the work into small ordered tasks
    with acceptance criteria and checkpoints, and save the result to
    tasks/plan.md and tasks/todo.md, or to an external issue tracker if the
    project names one.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low other (claude review: model text, it can be wrong): The skill tells the agent to create one item per task in an external issue tracker (examples given include GitHub Issues, Jira, Linear and bd/beads) when either the user or the project's agent rules files (CLAUDE.md, AGENTS.md) name one. When the trigger is a rules file, the agent acts through the user's third-party tracker account without the user asking for it in the current session, and items appear in a shared tracker. The skill does say not to bulk-close or delete another plan's open items. Nothing in it is malicious, and this fits a planning tool.

## Fix applied

- Fix label: hygiene
- Targets: low other
- After the fix: low other (claude review): \~ targeted, not re-verified
- Fix id: sha256:16eaf7cddd61e021e7dbf481f917417d09ca63a3b16c5e3e19937209a616998e
- Changed: SKILL.md
