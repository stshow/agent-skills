# esr review: skills/git-workflow-and-versioning

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 92d87ae1fe98e6b67403bace2ef01264f9664468
- Date: 2026-10-25
- Choice: fix (re-checked and applied)

## What it does (claude review, model text)

    A guidance-only skill that describes git workflow practices: atomic commits,
    commit message conventions, short-lived branches, worktrees for parallel
    agent work, pre-commit checks, debugging with git, semantic versioning,
    tagging and changelogs. It has a single SKILL.md file with no scripts.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 247): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 229): SKILL.md runs an npm package through npx without pinning its version
- low mutable_dependency (claude review: model text, it can be wrong): The pre-commit checklist runs \`npx tsc --noEmit\` without a version. If the project already has TypeScript installed, npx runs the local copy. If it does not, npx may download and run whatever package is currently published under the name 'tsc' from the registry, which is not the official TypeScript compiler package.
- low unsafe_execution (claude review: model text, it can be wrong): The skill tells the agent to use \`git reset --hard HEAD\` to return to the last good state when it 'goes off the rails', and to revert to the last commit when a test fails. A hard reset throws away all uncommitted changes in the working tree, and that can include work the user made outside the agent's changes.
- low other (claude review: model text, it can be wrong): The skill includes pushing tags and branches to a remote (\`git push origin v1.4.0\`), and its description triggers it on pushing to a remote and on cutting releases. A push uses the user's git credentials and account on a third-party hosting service, and a pushed release tag is visible to the project's users. The content does not limit pushes to cases the user asked for.
- info excessive_capability (claude review: model text, it can be wrong): The description says 'Use when making any code change' and the body says 'Always. Every code change flows through git.' This makes the skill load for almost every coding task, so its git guidance (committing, resetting, worktrees) applies even when the user did not ask for any git actions.

## Fix applied

- Fix label: hygiene
- Targets: low mutable\_dependency
- Targets: low mutable\_dependency
- Targets: low unsafe\_execution
- Targets: low other
- After the fix: low credential\_access (esr rules): – not addressed
- After the fix: low mutable\_dependency (esr rules): ✗ still there
- After the fix: low mutable\_dependency (claude review): \~ targeted, not re-verified
- After the fix: low unsafe\_execution (claude review): \~ targeted, not re-verified
- After the fix: low other (claude review): \~ targeted, not re-verified
- After the fix: info excessive\_capability (claude review): – not addressed
- Fix id: sha256:fd6b26cf6d3c73c45f3dcd413609ea764c045ee96561c37f26f23a853b913fbc
- Changed: SKILL.md
