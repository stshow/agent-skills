# esr review: skills/browser-testing-with-devtools

Written by esr (`esr owner/repo`) from its own records. It never quotes the skill beyond what a finding's text holds; the summary and the claude review's findings below are model text.

- Upstream: addyosmani/agent-skills
- Upstream commit reviewed: aeac41d4d005999432bb7312f7ff06383a91d59d
- Skill tree reviewed: 42be59520831f02c46bce7bed1aac6ab0592947c
- Date: 2026-10-25
- Choice: keep

## What it does (claude review, model text)

    A guidance-only skill that teaches the agent to test and debug web pages in
    a real Chrome browser through the chrome-devtools MCP server: screenshots,
    DOM, console, network, performance and accessibility checks. It also sets
    security rules for treating browser content as untrusted data and limiting
    page JavaScript execution.

## What it could do (static profile)

- reaches http hosts: localhost

## Public scores (outside opinions)

- public scores (outside opinions): Gen safe, Socket safe (0 alerts), Snyk medium; BAD: Snyk medium

## Findings

- high instruction_override (esr rules; rule instruction-override in SKILL.md line 77): SKILL.md tries to override the agent's instructions
- low mutable_dependency (esr rules; rule unpinned-npx in SKILL.md line 41): SKILL.md runs an npm package through npx without pinning its version
- low mutable_dependency (claude review: model text, it can be wrong): The setup tells the user to add an MCP server entry that runs \`npx -y chrome-devtools-mcp@latest\`. Because of \`@latest\`, every launch can fetch and run whatever version of the npm package is newest at that moment, and \`-y\` skips npx's install prompt. A compromised or changed release of the package would run with the user's privileges and full control of the browser it starts.
- low excessive_capability (claude review: model text, it can be wrong): The skill describes an optional \`--autoConnect\` mode that attaches the agent to the user's running Chrome. The skill itself says this exposes all open windows of the default profile, including logged-in email, banking and GitHub sessions and saved cookies. The skill recommends the isolated profile by default and gives rules against reading credentials. Those rules are advisory text, though: once this mode is enabled, nothing technical stops the page JavaScript tool from reaching authenticated sessions.

## Fix applied

- none
