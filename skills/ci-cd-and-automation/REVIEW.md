# esr review: skills/ci-cd-and-automation

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 34db321777a17e268ac425f0f7f2501dda55c955
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    A guidance-only skill for setting up and changing CI/CD pipelines. It
    describes quality gates, gives example GitHub Actions workflows (lint, type
    check, tests, build, audit, integration and E2E jobs), and covers deployment
    strategies, rollback, secrets handling and how to feed CI failures back to
    an agent. It ships no scripts.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 275): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 88): SKILL.md runs an npm package through npx without pinning its version
- low mutable_dependency (claude review: model text, it can be wrong): The example workflows call npm tools through npx with no pinned version (npx vercel, npx vercel rollback, npx playwright install/test, npx prisma, npx tsc). They also reference GitHub Actions by floating major tags such as actions/checkout@v4. When a tool is not already a pinned project dependency, npx downloads whatever version is current at run time. CI files the agent writes from these templates would then run code that can change between runs, and the Vercel steps get the VERCEL\_TOKEN secret.

## Fix applied

- none
