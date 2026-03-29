---
epistemic-status: budding
---

There are four fundamental interaction modes when interacting with AI. 

|  | | | | |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| **Name** | **Lookup** | **Workshop** | **Companion** | **Mission** |
| **Mode** | **one-off questions:**<br>user sends question, agent answers. no context kept between questions. | **ephemeral sessions:**<br>user and agent work together toward a goal. context is shared within the session, discarded when it ends. | **persistent sessions:**<br>ongoing collaboration with context that accumulates across sessions. | **autonomous task sessions:**<br>agent takes a task definition incl. definition of done, works independently, only asks user for approvals. |
| **Surface** | messenger, no threads | web UI + coding agent + git repo + git worktrees | web ui + coding agent + git repo | GitHub issues + PRs +  Kanban |
| **Example Tooling** | [NanoClaw](https://github.com/qwibitai/nanoclaw) | [Clay](https://github.com/chadbyte/clay) sessions/worktrees based on GitHub issues | Clay | ? |
