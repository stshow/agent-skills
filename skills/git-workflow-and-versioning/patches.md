# esr Patch log: skills/git-workflow-and-versioning

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:8056bf5db34da0d000a3816b3d31a18fafb39a126e920dcfe0170086aad86f91
- Reason: Model-proposed fix for sf-0002, l1-fnd-41a45307b9a1b7e965cd58ef; Model-proposed fix for l1-fnd-4ddbd8cb34bf9b6145cf0614; Model-proposed fix for l1-fnd-f2add6c992ca35365739c48e
- Upstream commit: aeac41d4d005999432bb7312f7ff06383a91d59d
- Resolves: rule destructive-git-guidance in SKILL.md
- Resolves: rule remote-push-guidance in SKILL.md
- Resolves: rule unpinned-npx in SKILL.md

Changes SKILL.md: 2 line(s) removed and 4 line(s) added, in 3 place(s).

Added:

    +This pattern means you never lose more than one increment of work. If an agent goes off the rails, `git restore --staged --worktree -- <files you changed>` takes those files back to the last successful state without discarding other uncommitted work in the tree.
    +npx --no-install tsc --noEmit   # runs only the project's installed TypeScript; never downloads a package
    +
    +Push tags and branches to a remote only when the user asked for a push or release in the current task.

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"This pattern means you never lose more than one increment of work. If an agent goes off the rails, `git restore --staged --worktree -- <files you changed>` takes those files back to the last successful state without discarding other uncommitted work in the tree.\n","at":3,"remove":1}],"old_bytes":263,"old_digest":"sha256:168535e62a1a06d161d246c4ce3df097af3e951bd761a523029d9ae8d964ff9e","old_lines":7},{"edits":[{"add":"npx --no-install tsc --noEmit   # runs only the project's installed TypeScript; never downloads a package\n","at":3,"remove":1}],"old_bytes":89,"old_digest":"sha256:1afc8548344ae07643b4c4dd2cfab1481d7093194a380832426d1508c814dc6c","old_lines":7},{"edits":[{"add":"\nPush tags and branches to a remote only when the user asked for a push or release in the current task.\n","at":3,"remove":0}],"old_bytes":210,"old_digest":"sha256:d1f7319d20ee5f3ef9797841f1e403bda265fbfb8dc392c96bd63c8307e02b37","old_lines":6}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for sf-0002, l1-fnd-41a45307b9a1b7e965cd58ef; Model-proposed fix for l1-fnd-4ddbd8cb34bf9b6145cf0614; Model-proposed fix for l1-fnd-f2add6c992ca35365739c48e","resolved":[{"file":"SKILL.md","rule":"destructive-git-guidance"},{"file":"SKILL.md","rule":"remote-push-guidance"},{"file":"SKILL.md","rule":"unpinned-npx"}],"upstream_commit":"aeac41d4d005999432bb7312f7ff06383a91d59d"},"id":"sha256:8056bf5db34da0d000a3816b3d31a18fafb39a126e920dcfe0170086aad86f91"}],"skill":"skills/git-workflow-and-versioning","version":1}
```
