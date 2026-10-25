# esr review: skills/test-driven-development

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: c7d844f3f2321c14e982346580742b17db2caf1a
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    An instruction-only skill that teaches the agent test-driven development:
    find the repository's own test tooling, write a failing test, make it pass,
    refactor, and reproduce bugs with tests before fixing them. It also gives
    guidance on test design, browser checks through DevTools, and using
    subagents to write reproduction tests.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- info other (claude review: model text, it can be wrong): The description tells the agent to use the skill for almost any code change: 'any logic', 'any bug', 'any behavior', and 'even when the code is pasted inline and the request does not mention tests'. This can make the agent apply the TDD workflow, and so create test files and run test commands, when the user only asked for a quick inline edit. Nothing here appears to be harmful.
- info coverage_gap (claude review: model text, it can be wrong): The skill points the agent to a reference file two directories above the skill root. That file was not part of the reviewed content, so what the agent would read there is unknown.

## Fix applied

- none
