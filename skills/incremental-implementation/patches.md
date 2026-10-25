# esr Patch log: skills/incremental-implementation

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:928a2c109f7e913f39367d444f6e0c92f10e33b22d0de3019757d03e80a16b7f
- Reason: Model-proposed fix for sf-0001, l1-fnd-a69e9a4b482c407155938dd9
- Upstream commit: aeac41d4d005999432bb7312f7ff06383a91d59d
- Resolves: rule unpinned-npx in SKILL.md

Changes SKILL.md: 1 line(s) removed and 1 line(s) added, in 1 place(s).

Added:

    +- [ ] Type checking passes, where the stack has one (`npx --no-install tsc --noEmit`, using the project's locally installed TypeScript, `mypy`, ...)

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"- [ ] Type checking passes, where the stack has one (`npx --no-install tsc --noEmit`, using the project's locally installed TypeScript, `mypy`, ...)\n","at":3,"remove":1}],"old_bytes":468,"old_digest":"sha256:90f09142c9562547499d254da08e03eaeb2a430b1a275e5a6b71d89b7f4f802e","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for sf-0001, l1-fnd-a69e9a4b482c407155938dd9","resolved":[{"file":"SKILL.md","rule":"unpinned-npx"}],"upstream_commit":"aeac41d4d005999432bb7312f7ff06383a91d59d"},"id":"sha256:928a2c109f7e913f39367d444f6e0c92f10e33b22d0de3019757d03e80a16b7f"}],"skill":"skills/incremental-implementation","version":1}
```
