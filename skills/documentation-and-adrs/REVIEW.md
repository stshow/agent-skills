# esr review: skills/documentation-and-adrs

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 4eacd38e5198110d740bb3172804059b8c3e6c94
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    An instruction-only skill that guides the agent in writing Architecture
    Decision Records, inline code comments, API docs, READMEs, changelogs and
    agent rules files, following the conventions the repository already uses.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 212): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)

## Fix applied

- none
