# esr review: skills/deprecation-and-migration

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 452a130309afc52a26beceb21f1467936e53a37c
- Date: 2026-10-25
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A guidance-only skill about deprecating and migrating software. It explains
    when to deprecate, how to announce deprecations and move consumers
    incrementally, migration patterns (strangler, adapter, feature flags),
    expand/contract database schema migrations, and checklists for verifying the
    work.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 91): SKILL.md runs an npm package through npx without pinning its version
- info mutable_dependency (claude review: model text, it can be wrong): An example deprecation-notice template has a migration step that runs \`npx migrate-check\` with no pinned version. The command is part of sample notice text written for human readers. It is not an instruction telling the agent to run anything. Still, an agent that copies the template, or treats its steps as actions, could pull and run whatever package currently has that name in the npm registry.

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- After the fix: low mutable\_dependency (esr rules): ✓ gone (re-scanned)
- After the fix: info mutable\_dependency (claude review): – not addressed
- Fix id: sha256:533a7d46c9ed7ab0a382d92695da6375b31284731586cbdfeff9e059ebbce1f8
- Changed: SKILL.md
