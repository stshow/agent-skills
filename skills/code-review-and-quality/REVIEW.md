# esr review: skills/code-review-and-quality

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 2c0b966d411b0d64c4f44efdde30d5f6f3666f76
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    An instruction-only skill that guides the agent through a code review on
    five axes (correctness, readability, architecture, security, performance).
    It also covers change sizing, review comment labels, dead-code hygiene and
    checks on dependency upgrades.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- high concealment (esr rules; rule conceal-from-user in SKILL.md line 241): SKILL.md tells the agent to hide its actions from the user

## Fix applied

- none
