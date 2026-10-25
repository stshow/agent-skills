# esr Patch log: skills/context-engineering

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:b55ebc83c103c839010b7f9ac372515f78afc8bd78a51169115121c41e3c67ee
- Reason: Model-proposed fix for sf-0002
- Upstream commit: aeac41d4d005999432bb7312f7ff06383a91d59d
- Resolves: rule unpinned-npx in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +- Type check: `npx --no-install tsc --noEmit`

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"- Type check: `npx --no-install tsc --noEmit`\n","at":3,"remove":1}],"old_bytes":180,"old_digest":"sha256:e41ab0bfe1d34ffe380a2f47a7ec61940e2bc8519892e59729a3c6f42aae2d08","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for sf-0002","resolved":[{"file":"SKILL.md","rule":"unpinned-npx"}],"upstream_commit":"aeac41d4d005999432bb7312f7ff06383a91d59d"},"id":"sha256:b55ebc83c103c839010b7f9ac372515f78afc8bd78a51169115121c41e3c67ee"}],"skill":"skills/context-engineering","version":1}
```
