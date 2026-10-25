# esr Patch log: skills/deprecation-and-migration

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:404038cf58c3dc615e6d8a7a7c3a0ad66d6b49937c65448878b3c4fb8ee5ae67
- Reason: Model-proposed fix for sf-0001
- Upstream commit: aeac41d4d005999432bb7312f7ff06383a91d59d
- Resolves: rule unpinned-npx in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +3. Run the project's own checked-in migration verification script: `npm run migrate-check`

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"3. Run the project's own checked-in migration verification script: `npm run migrate-check`\n","at":3,"remove":1}],"old_bytes":260,"old_digest":"sha256:d819b806a3249e2fb96f001a11f8b86c242a151740170bc7ba114b87cb7218d8","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for sf-0001","resolved":[{"file":"SKILL.md","rule":"unpinned-npx"}],"upstream_commit":"aeac41d4d005999432bb7312f7ff06383a91d59d"},"id":"sha256:404038cf58c3dc615e6d8a7a7c3a0ad66d6b49937c65448878b3c4fb8ee5ae67"}],"skill":"skills/deprecation-and-migration","version":1}
```
