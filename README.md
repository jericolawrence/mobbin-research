# mobbin-research

A skill that makes your coding agent research UI/UX directions on Mobbin before anyone writes
product code. It reads your current interface, interviews you on the decisions that matter, searches
Mobbin broadly, and hands back 4–5 strong references plus 3 playable demos to compare. Then it asks
you to pick a direction.

Works with Claude Code, Codex and Cursor.

## Install

**Claude Code plugin**

```
/plugin marketplace add jericolawrence/mobbin-research
/plugin install mobbin-research@mobbin-research
```

**Skills CLI** (Claude Code, Codex, Cursor), run from the root of your repo:

```bash
npx skills add jericolawrence/mobbin-research -a claude-code
```

Add `-a codex -a cursor` for those agents.

**Manual**: copy `skills/mobbin-research/` into `~/.claude/skills/` (or your repo's
`.claude/skills/`).

## Use it

```
/mobbin-research Research a smoother transition into conversation search in my SwiftUI app.
Right now tapping the search button switches abruptly. Show me references and demos.
```

In Codex, use `$mobbin-research`.

## What it does

1. **Investigates first.** Reads the prompt, screenshots, repo instructions and the relevant UI code. Asks only what evidence can't settle.
2. **Grills you on the brief.** Numbered questions, each with a recommended answer, until goal, platform, baseline, feel, constraints, success criteria and demo format are agreed.
3. **Searches broadly, inspects deeply.** Screen, flow and section searches on Mobbin, with a search ledger, deduplication and a stop rule. Platform docs back up any claim about native behavior.
4. **Delivers a short list.** 4–5 cited references, a comparison, 3 playable demos kept apart from product code, a recommendation and a saved Markdown report.
5. **Grills you on direction.** Plans or builds only when you say so.

It keeps evidence honest: what was observed, documented, inferred or proposed stays labelled, and
Mobbin stills are never passed off as proof of timing or easing.

## Requirements

- The **Mobbin connector** (MCP) with `search_screens`, `search_flows` and `search_sections`, and a
  Mobbin account. Without it the skill falls back to permitted browser access and reports gaps.
- Optional: a `grilling` skill and a `research` skill (for example from
  [mattpocock/skills](https://github.com/mattpocock/skills)). The skill carries its own fallback
  for both.

## License

MIT
