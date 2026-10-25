# esr Patch log: skills/doubt-driven-development

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:190c05d9f93038fbded1fa140b4b652935b060583b5cf98d81b876fbdab3f9d9
- Reason: Model-proposed fix for l1-fnd-348629bd4d5d0e89b68a66d6
- Upstream commit: aeac41d4d005999432bb7312f7ff06383a91d59d
- Resolves: rule Fixed, predictable temp-file name in a shared directory used for the review prompt in SKILL.md

Changes SKILL.md: 3 line(s) removed and 7 line(s) added, in 1 place(s).

Added:

    +# Write the adversarial prompt + ARTIFACT + CONTRACT to a private temp file
    +# from mktemp (unique name, owner-only permissions), never a fixed shared name.
    +PROMPT_FILE="$(mktemp)"
    +codex exec --sandbox read-only -C <repo-path> - < "$PROMPT_FILE"
    +gemini --approval-mode plan -p "" < "$PROMPT_FILE"
    +
    +rm -f "$PROMPT_FILE"

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"# Write the adversarial prompt + ARTIFACT + CONTRACT to a private temp file\n# from mktemp (unique name, owner-only permissions), never a fixed shared name.\nPROMPT_FILE=\"$(mktemp)\"\n","at":3,"remove":1},{"add":"codex exec --sandbox read-only -C <repo-path> - < \"$PROMPT_FILE\"\n","at":7,"remove":1},{"add":"gemini --approval-mode plan -p \"\" < \"$PROMPT_FILE\"\n\nrm -f \"$PROMPT_FILE\"\n","at":11,"remove":1}],"old_bytes":819,"old_digest":"sha256:fa86faa36161abc6cf708be3f4c0e0896a6a59266bf1364bd432e48589897a9d","old_lines":15}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-348629bd4d5d0e89b68a66d6","resolved":[{"file":"SKILL.md","rule":"Fixed, predictable temp-file name in a shared directory used for the review prompt"}],"upstream_commit":"aeac41d4d005999432bb7312f7ff06383a91d59d"},"id":"sha256:190c05d9f93038fbded1fa140b4b652935b060583b5cf98d81b876fbdab3f9d9"}],"skill":"skills/doubt-driven-development","version":1}
```
