---
name: Never create files with non-breaking spaces or special characters
description: Always use regular spaces and alphanumeric characters for filenames
type: feedback
---

When creating or renaming files, use only regular spaces and standard characters. Avoid non-breaking spaces (U+00A0), ligatures, or other Unicode lookalikes that can cause duplicate files and tool failures.

**Why:** Non-breaking spaces are invisible in some contexts, causing duplicates to appear identical but actually be different files. This leads to content duplication and confusion.

**How to apply:** When creating/renaming files, use `cp` or `mv` with normal spaces only. If a filename already has weird chars, use `find` + `delete` to clean up, then recreate with plain ASCII spaces. Never use the Edit tool for files with weird filenames—use bash `cat`/`sed`/file operations instead.
