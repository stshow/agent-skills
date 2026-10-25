# esr review: skills/security-and-hardening

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: f9f5b22b97f1f0bfe47a30c0ac860c343e332a94
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    A guidance-only skill for building and reviewing secure web applications. It
    covers threat modelling, OWASP-style controls, secrets handling, dependency
    and supply-chain auditing, privacy, and LLM feature hardening. Example code
    patterns sit in a reference file that is loaded on demand.

## What it could do (static profile)

- reaches http hosts: localhost
- reaches https hosts: genai.owasp.org

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk low

## Findings

- low credential_access (esr rules; rule credential-path in SKILL.md line 129): SKILL.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- low credential_access (esr rules; rule credential-path in references/hardening-patterns.md line 276): references/hardening-patterns.md references a credential store (SSH keys, cloud or token files, browser cookies, .env)
- info coverage_gap (claude review: model text, it can be wrong): The skill tells the agent to read a shared checklist outside its own directory (\`../../references/security-checklist.md\`, and \`../../../references/security-checklist.md\` from the reference file). That file was not part of the reviewed content, so nothing is known about the instructions it gives the agent once loaded. The paths are relative, so they resolve inside the package's own tree. There is no sign of credential or unrelated file access.

## Fix applied

- none
