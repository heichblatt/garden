---
tags:
  - epistemic-status:budding
---

To [[AI|onboard agentic colleagues into existing teams]] we need them to continually improve themselves, by learning from the real world, reflecting on those memories and adapting its behaviour according to insights from reflecting.

Self-improvement requires

- agent being involved in actual collaboration and/or agent has access to human knowledge bases to generate raw material
- its own persistent memory
- a mechanism to reason and reflect on memories regularly and distill knowledge or surface insights

## Approaches

There are several approaches to this.

1. [Karpathy's AI Librarian](https://venturebeat.com/data/karpathy-shares-llm-knowledge-base-architecture-that-bypasses-rag-with-an) has been the most influential. It uses a knowledge-base-in-context approach where the system maintains a working memory of relevant information and retrieves it as needed. [Karpathy later expanded on the idea with LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). A very early version can be seen in The ["append-and-review note"](https://karpathy.bearblog.dev/the-append-and-review-note/).
    - [Marciuo Puga's Cog](https://github.com/marciopuga/cog), a prototypical "plain-text cognitive architecture for Claude Code". (I also like his blogging ([[Think in Public]]) while developing it in a [separate blog only for Cog.](https://lab.puga.com.br/cog/#/journal)
    - [GitAgent](https://www.gitagent.sh/) approaches this from the repo-side: defining agents in Git repos, including memory and reflection.
    - [Brenno Ferrari's obsidian-mind](https://github.com/breferrari/obsidian-mind), the same basic idea but simpler and clearly scoped to an Obsidian-based agent.
    - Claude Code has a built-in memory management (["Auto Memory"](https://code.claude.com/docs/en/memory#auto-memory)) and the 2026 Claude Code source leak ([news post](https://arstechnica.com/ai/2026/03/entire-claude-code-cli-source-code-leaks-thanks-to-exposed-map-file/), [analysis](https://nitter.net/himanshustwts/status/2038924027411222533)), confirmed the idea: 3-layer design and Claude's internal "autoDream": background memory rewriting.
    - [Piskala et al.: From Everything-is-a-File to Files-Are-All-You-Need: How Unix Philosophy Informs the Design of Agentic AI Systems](https://arxiv.org/abs/2601.11672) explains how the principles of simplicity and composability, enshrined in the [UNIX philosophy](https://en.wikipedia.org/wiki/Unix_philosophy) give us established tools and processes to interact with text.
2. classic architecture with LLM, RAG and MCP
