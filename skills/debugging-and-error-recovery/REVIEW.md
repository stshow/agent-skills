# esr review: skills/debugging-and-error-recovery

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: c3b5c340bae3ac952733213b40035820acfb48a3
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    An instruction-only guide that walks the agent through structured root-cause
    debugging when tests fail, builds break or errors appear. The steps are
    reproduce, localize, reduce, fix, guard with a regression test, and verify,
    using the repository's own test and build commands and git bisect.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- none

## Fix applied

- none
