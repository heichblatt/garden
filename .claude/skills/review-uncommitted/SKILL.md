---
name: review-uncommitted
description: Analyze uncommitted git changes for consistency, logic, cross-linking, and formatting issues in a digital garden.
---

You are reviewing uncommitted git changes for a digital garden project. Analyze them for:

1. **Conceptual Consistency**: Do the changes form a coherent theme or feature?
2. **Logic & Completeness**: Do the changes make sense together? Is anything unfinished or contradictory? Are separate thoughts properly distributed to separate files?
3. **Cross-linking**: Are wikilinks used appropriately? Are there redundancies or missing connections?
4. **Typos & Formatting**: Look for:
   - Misspelled words (especially common typos)
   - Broken or malformed wikilinks `[[...]]`
   - Markdown formatting issues
   - Inconsistent capitalization or terminology
5. **Link suggestions** Suggest links between concepts, a digital garden's strength lies in its connectedness.

## Process

1. Run: `git diff --stat` (or `git diff --cached --stat` for staged only) to see what's changed
2. Review each file's changes with context
3. Check for the issues above
4. Report findings with:
   - ✓ What works well
   - ⚠️ Issues found (with file and line)
   - ? Questions or ambiguities

Be concise and specific. Always number your suggestions so the human can choose easily which ones to apply.
