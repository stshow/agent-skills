# esr review: skills/doubt-driven-development

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 2a25398c4f73f715c1fe5110ca789fdb7de30983
- Date: 2026-10-25
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A process-discipline skill: before a non-trivial decision stands, the agent
    states the claim, pulls out the artifact and its contract, has a fresh-
    context subagent review them adversarially, then reconciles the findings,
    with at most 3 cycles. In interactive sessions it can also offer a second
    review through an external CLI (Gemini or Codex), but only after the user
    authorizes it.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low path_handling (claude review: model text, it can be wrong): The example commands write the prompt, which includes the code artifact under review, to one fixed, predictable file name in the shared temporary directory, then pipe that file into the external CLI. On a multi-user machine, another local user could read that file or plant it ahead of time (for example as a symlink). That could expose proprietary code, or swap in different content for the prompt sent to the reviewer CLI.
- low undeclared_egress (claude review: model text, it can be wrong): When the user picks a cross-model review, the skill runs a third-party model CLI (Gemini or Codex) and passes it the artifact and contract. Those are likely code from the user's workspace, and the CLI may send them to an external model provider. The functionality contract lists no external services. The skill requires the user to opt in explicitly, confirm the exact command, and authorize each run separately. It also says to skip this step in non-interactive contexts.

## Fix applied

- Fix label: hygiene
- Targets: low path\_handling
- After the fix: low path\_handling (claude review): \~ targeted, not re-verified
- After the fix: low undeclared\_egress (claude review): – not addressed
- Fix id: sha256:ac7921a985c76bc137883d94a7b88d95f7b851d135453be86100c2f548e5ccdb
- Changed: SKILL.md
