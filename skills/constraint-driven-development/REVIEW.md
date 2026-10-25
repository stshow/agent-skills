# esr review: skills/constraint-driven-development

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 8aa3f6a661bc7931f86282ad33e33724932ce490
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    The skill helps a user set a project's quality bar. It asks up to four
    questions, writes a CONSTRAINTS.md file with thresholds, installs and wires
    up standard checking tools (type checkers, linters, coverage, Semgrep,
    gitleaks, osv-scanner, Lighthouse, axe), and uses a diff-scoped "floor
    guard" to catch an agent lowering the bar.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low mutable_dependency (esr rules; rule unpinned-install in SKILL.md line 149): SKILL.md installs a package without pinning its version, so its code can change at any time
- low mutable_dependency (claude review: model text, it can be wrong): Step 4 tells the agent to install checking tools with pip, pipx, brew and npm and gives no version for any of them (mypy, pytest-cov, semgrep, gitleaks, osv-scanner, lighthouse, size-limit, @axe-core/cli, dependency-cruiser, @stryker-mutator/core). Semgrep is also run with registry rule packs (p/default, p/owasp-top-ten) that are downloaded when it runs. The code that gets installed and run can therefore change over time. gitleaks and osv-scanner are installed for the whole machine through brew; the skill points this out itself and offers running them only in CI.
- info persistence (claude review: model text, it can be wrong): The skill tells the agent to add a standing instruction to AGENTS.md and CLAUDE.md ('Read CONSTRAINTS.md before writing code. Do not weaken it to make a change pass.'), and suggests wiring check scripts into the agent's post-edit hook and CI. These changes persist into future agent sessions. The added text is shown in full, it serves the stated purpose, and it does not hide anything or override the user.

## Fix applied

- none
