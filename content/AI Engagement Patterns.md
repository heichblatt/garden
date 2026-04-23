---
tags:
  - epistemic-status:evergreen
---

There are at least four fundamental engagement patterns when working with AI.

The main differences are:

- context scope: what information is kept and for how long
- surface: tool/paradigm AI and human use to interact and [[AI-Human Collaboration|collaborate]]

| | **Mode** | **Surface** | **Example Tooling** |
| ----------- | ----------- | ----------- | ----------- |
| **Lookup** | **one-off questions:**<br>user sends question, agent answers. no context kept between questions. | messenger, no threads | AI capabilities built into applications, i.e. Google's AI summary |
| **Workshop** | **ephemeral sessions:**<br>user and agent work together toward a goal. context is shared within the session, discarded when it ends. | web UI + coding agent + git repo + git worktrees | [Clay](https://github.com/chadbyte/clay) sessions/worktrees based on GitHub issues |
| **Companion** | **persistent sessions:**<br>ongoing collaboration with context that accumulates across sessions. | web ui + coding agent + git repo | [NanoClaw](https://github.com/qwibitai/nanoclaw), Clay |
| **Mission** | **autonomous task sessions:**<br>agent takes a task definition incl. definition of done, works independently, only asks user for approvals. | GitHub issues + PRs +  Kanban | ? |

## Notes

- I think there is a pattern beyond "Mission" that adds another strategic layer on top, examples are [Linear.app](https://linear.app) and [Dan Meisner's "Mission Control"](https://github.com/MeisnerDan/mission-control). I'm not sure yet if that is an extension of "Mission" or something separate.
- Different engagement patterns require different [[Personal AI Infrastructure]] — each pattern has distinct needs for routing, cost, and capability.
