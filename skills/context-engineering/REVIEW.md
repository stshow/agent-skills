# esr review: skills/context-engineering

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 5da63415256218e76f85e7e371bb21ceef4293e1
- Date: 2026-10-25
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An instruction-only guide that teaches the agent how to manage its context:
    writing project rules files such as CLAUDE.md, loading only the specs and
    source files a task needs, trimming and summarising long sessions, and
    asking about ambiguity instead of guessing.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 65): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 55): SKILL.md runs an npm package through npx without pinning its version

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- After the fix: low credential\_access (esr rules): – not addressed
- After the fix: low mutable\_dependency (esr rules): ✗ still there
- Fix id: sha256:8d52eb8736122dd97c7aa9f93dbbb81f1014c49718832c4cc8e2b72547364ca9
- Changed: SKILL.md
