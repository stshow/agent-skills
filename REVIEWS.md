# esr reviews

Every skill in addyosmani/agent-skills at commit aeac41d4d005999432bb7312f7ff06383a91d59d, reviewed on 2026-10-25, with its Choice. A dropped skill is not on this branch.

| Skill | Choice | Review |
| --- | --- | --- |
| skills/api-and-interface-design | keep | [REVIEW.md](skills/api-and-interface-design/REVIEW.md) |
| skills/browser-testing-with-devtools | keep | [REVIEW.md](skills/browser-testing-with-devtools/REVIEW.md) |
| skills/ci-cd-and-automation | keep | [REVIEW.md](skills/ci-cd-and-automation/REVIEW.md) |
| skills/code-review-and-quality | keep | [REVIEW.md](skills/code-review-and-quality/REVIEW.md) |
| skills/code-simplification | keep | [REVIEW.md](skills/code-simplification/REVIEW.md) |
| skills/constraint-driven-development | keep | [REVIEW.md](skills/constraint-driven-development/REVIEW.md) |
| skills/context-engineering | fix (re-checked and applied) | [REVIEW.md](skills/context-engineering/REVIEW.md) |
| skills/debugging-and-error-recovery | keep | [REVIEW.md](skills/debugging-and-error-recovery/REVIEW.md) |
| skills/deprecation-and-migration | fix (re-checked and applied) | [REVIEW.md](skills/deprecation-and-migration/REVIEW.md) |
| skills/documentation-and-adrs | keep | [REVIEW.md](skills/documentation-and-adrs/REVIEW.md) |
| skills/doubt-driven-development | fix (re-checked and applied) | [REVIEW.md](skills/doubt-driven-development/REVIEW.md) |
| skills/frontend-ui-engineering | keep | [REVIEW.md](skills/frontend-ui-engineering/REVIEW.md) |
| skills/git-workflow-and-versioning | fix (re-checked and applied) | [REVIEW.md](skills/git-workflow-and-versioning/REVIEW.md) |
| skills/idea-refine | keep | [REVIEW.md](skills/idea-refine/REVIEW.md) |
| skills/incremental-implementation | fix (re-checked and applied) | [REVIEW.md](skills/incremental-implementation/REVIEW.md) |
| skills/interview-me | keep | [REVIEW.md](skills/interview-me/REVIEW.md) |
| skills/observability-and-instrumentation | keep | [REVIEW.md](skills/observability-and-instrumentation/REVIEW.md) |
| skills/performance-optimization | keep | [REVIEW.md](skills/performance-optimization/REVIEW.md) |
| skills/planning-and-task-breakdown | fix (re-checked and applied) | [REVIEW.md](skills/planning-and-task-breakdown/REVIEW.md) |
| skills/security-and-hardening | keep | [REVIEW.md](skills/security-and-hardening/REVIEW.md) |
| skills/shipping-and-launch | keep | [REVIEW.md](skills/shipping-and-launch/REVIEW.md) |
| skills/source-driven-development | drop | dropped from this branch |
| skills/spec-driven-development | keep | [REVIEW.md](skills/spec-driven-development/REVIEW.md) |
| skills/test-driven-development | keep | [REVIEW.md](skills/test-driven-development/REVIEW.md) |
| skills/using-agent-skills | keep | [REVIEW.md](skills/using-agent-skills/REVIEW.md) |

## Warnings

Warning: kept skills still reference skills you dropped (no Choice changes):

- skills/doubt-driven-development references source-driven-development (dropped: skills/source-driven-development)
- skills/interview-me references source-driven-development (dropped: skills/source-driven-development)
- skills/using-agent-skills references source-driven-development (dropped: skills/source-driven-development)

## Findings of skills not on this branch

### skills/source-driven-development: drop

- high instruction_override (esr rules; rule instruction-override in SKILL.md line 110): SKILL.md tries to override the agent's instructions

esr reads the block below on the next run to remember these Choices; editing it makes esr ask again.

```esr-choices
{"commit":"aeac41d4d005999432bb7312f7ff06383a91d59d","skills":[{"choice":"keep","fix":null,"siblings":[],"skill":"skills/api-and-interface-design","tree":"3234ce9609d7ce2fc49b2a51fb64e118d20c7e85"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/browser-testing-with-devtools","tree":"42be59520831f02c46bce7bed1aac6ab0592947c"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/ci-cd-and-automation","tree":"34db321777a17e268ac425f0f7f2501dda55c955"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/code-review-and-quality","tree":"2c0b966d411b0d64c4f44efdde30d5f6f3666f76"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/code-simplification","tree":"15b6e21924188ee46402a8c91963162fd9056c7d"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/constraint-driven-development","tree":"8aa3f6a661bc7931f86282ad33e33724932ce490"},{"choice":"fix","fix":"sha256:8d52eb8736122dd97c7aa9f93dbbb81f1014c49718832c4cc8e2b72547364ca9","siblings":[],"skill":"skills/context-engineering","tree":"5da63415256218e76f85e7e371bb21ceef4293e1"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/debugging-and-error-recovery","tree":"c3b5c340bae3ac952733213b40035820acfb48a3"},{"choice":"fix","fix":"sha256:533a7d46c9ed7ab0a382d92695da6375b31284731586cbdfeff9e059ebbce1f8","siblings":[],"skill":"skills/deprecation-and-migration","tree":"452a130309afc52a26beceb21f1467936e53a37c"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/documentation-and-adrs","tree":"4eacd38e5198110d740bb3172804059b8c3e6c94"},{"choice":"fix","fix":"sha256:ac7921a985c76bc137883d94a7b88d95f7b851d135453be86100c2f548e5ccdb","siblings":[],"skill":"skills/doubt-driven-development","tree":"2a25398c4f73f715c1fe5110ca789fdb7de30983"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/frontend-ui-engineering","tree":"39280620a66bfaf39ebe0aa032b8568c65f2b247"},{"choice":"fix","fix":"sha256:fd6b26cf6d3c73c45f3dcd413609ea764c045ee96561c37f26f23a853b913fbc","siblings":[],"skill":"skills/git-workflow-and-versioning","tree":"92d87ae1fe98e6b67403bace2ef01264f9664468"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/idea-refine","tree":"5dc24f2a92ec4ea91ad6cd56268e1bf0fef678bc"},{"choice":"fix","fix":"sha256:0b2fd158f9436296f4985438d9108306d90e4670feb2ebcd69180cf2d03fc6aa","siblings":[],"skill":"skills/incremental-implementation","tree":"a3e2fab3e3b97e078e2404a505c4b2fa5e123c9b"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/interview-me","tree":"2a391376521dee060881b7edc676e58a564616f2"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/observability-and-instrumentation","tree":"1e8f1c0144e2b8f7859f5870329a31f8abc58193"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/performance-optimization","tree":"c924947ef20bdf80fe7a0af2267e02215ecea4b8"},{"choice":"fix","fix":"sha256:16eaf7cddd61e021e7dbf481f917417d09ca63a3b16c5e3e19937209a616998e","siblings":[],"skill":"skills/planning-and-task-breakdown","tree":"3045f95a156dc71d7b5ac1e29ce795bb5cac2b71"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/security-and-hardening","tree":"f9f5b22b97f1f0bfe47a30c0ac860c343e332a94"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/shipping-and-launch","tree":"566523b5f1b266856c7ba6a89fda272e5cebc4f9"},{"choice":"drop","fix":null,"siblings":[],"skill":"skills/source-driven-development","tree":"29e1dcc180d54898aa7c5f4c466864c59ac2ee41"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/spec-driven-development","tree":"4d36b30efbe4109ed70f5933fb9cf97860786492"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/test-driven-development","tree":"c7d844f3f2321c14e982346580742b17db2caf1a"},{"choice":"keep","fix":null,"siblings":[],"skill":"skills/using-agent-skills","tree":"81e8196f4dd4bf9fc5f0a1b827f4148af52a4391"}],"upstream":"addyosmani/agent-skills","version":2}
```
