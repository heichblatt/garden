---
epistemic-status: budding
---

There are four fundamental interaction modes when interacting with AI. 

| | **Mode** | **Surface** | **Example Tooling** |
| ----------- | ----------- | ----------- | ----------- |
| **Lookup** | **one-off questions:**<br>user sends question, agent answers. no context kept between questions. | messenger, no threads | [NanoClaw](https://github.com/qwibitai/nanoclaw) |
| **Workshop** | **ephemeral sessions:**<br>user and agent work together toward a goal. context is shared within the session, discarded when it ends. | web UI + coding agent + git repo + git worktrees | [Clay](https://github.com/chadbyte/clay) sessions/worktrees based on GitHub issues |
| **Companion** | **persistent sessions:**<br>ongoing collaboration with context that accumulates across sessions. | web ui + coding agent + git repo | Clay |
| **Mission** | **autonomous task sessions:**<br>agent takes a task definition incl. definition of done, works independently, only asks user for approvals. | GitHub issues + PRs +  Kanban | ? |
