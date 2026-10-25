# esr review: skills/using-agent-skills

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 81e8196f4dd4bf9fc5f0a1b827f4148af52a4391
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    A meta-skill made of instructions only. It tells the agent which in-package
    engineering workflow skill to use for each development phase, and it sets
    general working rules: state assumptions, push back when warranted, keep
    scope tight and verify work.

## What it could do (static profile)

- no network hosts, tool grants, scripts or binaries found

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- info other (claude review: model text, it can be wrong): The description asks for the skill to be used whenever a session starts, and the body calls its behaviours 'non-negotiable' across all skills. This is a broad, always-on steer of agent behaviour. The content it steers toward is ordinary engineering practice, and it explicitly defers to the human's decision, so nothing harmful was found.
- info coverage_gap (claude review: model text, it can be wrong): The skill points the agent to a Definition of Done document at a relative path two levels above the skill directory (../../references/definition-of-done.md). That file is not among the skill's files and was not part of this review, so the agent may load and follow guidance whose content has not been checked.

## Fix applied

- none
