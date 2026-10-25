# esr review: skills/performance-optimization

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: c924947ef20bdf80fe7a0af2267e02215ecea4b8
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    An instruction-only guide that teaches the agent a measure-first way to
    optimize performance: profile, find the bottleneck, fix one thing, re-
    measure, then keep or revert. It covers frontend (Core Web Vitals, images,
    bundles, re-renders) and backend (N+1 queries, pagination, indexes,
    connection pools, caching), with worked examples in a reference file.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 206): SKILL.md runs an npm package through npx without pinning its version
- low mutable_dependency (claude review: model text, it can be wrong): Its 'Enforce in CI' example runs \`npx bundlesize\` and \`npx lhci autorun\` with no version pinned. If the agent runs these commands, or copies them into a CI configuration, npx may fetch and run whatever version of the package the registry serves at that moment.

## Fix applied

- none
