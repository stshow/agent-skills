# esr Patch log: skills/planning-and-task-breakdown

Every change made to this Upstream skill on this branch, in the order esr applies them to the Upstream text. Written by esr; esr reads the block at the end on the next run, and asks about any entry it did not record itself.

The lines an entry replaces are kept only as a hash, never as text. To see a whole change, run git diff from the entry's Upstream commit to this branch, limited to this skill's folder.

## 1. fix (hygiene)

- Id: sha256:ad8bb6bb2ab7cca904488d64e50a08a5a2ed466c7ecc0a6cc879d3a100084c9a
- Reason: Model-proposed fix for l1-fnd-55e8d1f25bdc846971a9533e
- Upstream commit: aeac41d4d005999432bb7312f7ff06383a91d59d
- Resolves: rule Project rules files, not only the user, can cause items to be created in third-party trackers in SKILL.md

Changes SKILL.md: 2 line(s) removed and 2 line(s) added, in 2 place(s).

Added:

    +- **External tracker:** if the user designates an issue tracker (e.g. GitHub Issues, Jira, Linear, `bd`/beads) in the current request, create one tracker item per task instead of writing `tasks/todo.md`; if only the project's agent rules (`CLAUDE.md`, `AGENTS.md`, etc.) name one, write `tasks/todo.md` and note the named tracker in `tasks/plan.md`. Map the Step 4 structure onto the tracker's fields: acceptance criteria and verification steps in the item body, dependencies via the tracker's linking mechanism (`bd dep add`, "blocked by", etc.). Record Step 5 checkpoints as tracker items too, or as a checklist in the plan document if the tracker has no natural equivalent.
    +- Writing `tasks/todo.md` when the user has designated an external tracker (or scattering tasks across both)

```esr-patches
{"entries":[{"entry":{"changes":[{"hunks":[{"edits":[{"add":"- **External tracker:** if the user designates an issue tracker (e.g. GitHub Issues, Jira, Linear, `bd`/beads) in the current request, create one tracker item per task instead of writing `tasks/todo.md`; if only the project's agent rules (`CLAUDE.md`, `AGENTS.md`, etc.) name one, write `tasks/todo.md` and note the named tracker in `tasks/plan.md`. Map the Step 4 structure onto the tracker's fields: acceptance criteria and verification steps in the item body, dependencies via the tracker's linking mechanism (`bd dep add`, \"blocked by\", etc.). Record Step 5 checkpoints as tracker items too, or as a checklist in the plan document if the tracker has no natural equivalent.\n","at":3,"remove":1}],"old_bytes":1199,"old_digest":"sha256:642bd883857895e86da2b182fc9787d688cf650d3d286537df647b15da4761cd","old_lines":7},{"edits":[{"add":"- Writing `tasks/todo.md` when the user has designated an external tracker (or scattering tasks across both)\n","at":3,"remove":1}],"old_bytes":414,"old_digest":"sha256:a12bf2163d53257a35876f878e4cda775564c26d53631331a8db9479a216ac03","old_lines":7}],"old_bytes":null,"old_digest":null,"op":"change","path":"SKILL.md"}],"kind":"fix (hygiene)","reason":"Model-proposed fix for l1-fnd-55e8d1f25bdc846971a9533e","resolved":[{"file":"SKILL.md","rule":"Project rules files, not only the user, can cause items to be created in third-party trackers"}],"upstream_commit":"aeac41d4d005999432bb7312f7ff06383a91d59d"},"id":"sha256:ad8bb6bb2ab7cca904488d64e50a08a5a2ed466c7ecc0a6cc879d3a100084c9a"}],"skill":"skills/planning-and-task-breakdown","version":1}
```
