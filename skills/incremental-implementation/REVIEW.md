# esr review: skills/incremental-implementation

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: a3e2fab3e3b97e078e2404a505c4b2fa5e123c9b
- Date: 2026-10-25
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    An instruction-only skill that tells the agent to build changes in thin,
    verifiable slices: implement a small piece, run the repository's tests,
    build, type-check and lint, then commit before moving to the next slice. It
    also covers slicing strategies, staying in scope, feature flags and keeping
    changes easy to roll back.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 206): SKILL.md runs an npm package through npx without pinning its version
- low mutable_dependency (claude review: model text, it can be wrong): The increment checklist gives \`npx tsc --noEmit\` as an example type-check command, with no version pinned. In a project that has TypeScript installed locally, npx uses that local copy. In a project that does not, npx may fetch and run whatever package is published on the registry under that name, which is not guaranteed to be the TypeScript compiler.

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- Targets: low mutable\_dependency
- After the fix: low mutable\_dependency (esr rules): ✗ still there
- After the fix: low mutable\_dependency (claude review): \~ targeted, not re-verified
- Fix id: sha256:0b2fd158f9436296f4985438d9108306d90e4670feb2ebcd69180cf2d03fc6aa
- Changed: SKILL.md
