# Mobbin tools and evidence

Discover current plugin tools and read their descriptions and schemas before calling them. The capabilities below were inspected on 2026-10-02; tool schemas take precedence if they change.

| Research need | Available tool | Expansion |
| --- | --- | --- |
| Interface states | `search_screens` (Mobbin connector) | `standard` for exploration, `deep` for nuanced matching; `exclude_screen_ids` avoids repeats |
| Journeys and neighboring states | `search_flows` (Mobbin connector) | `page` up to 20, while `has_next_page` is true |
| Website sections | `search_sections` (Mobbin connector) | `page`, while `has_next_page` is true |

Screens and flows currently support `ios` and `web`. Screen search has no pagination argument. Do not invent Android support, video tools, recording URLs, or parameters. If the target is unsupported, explain the gap and settle how reference platforms should relate to it.

## Query construction

Use one natural-language intent per call. Describe visible elements and their relationship for screens; describe the journey for flows. Set platform through its parameter. Use an app name in the query for app-specific follow-ups. Avoid mixed intents, negations, disconnected keyword lists, and vague aesthetic words.

For a search-entry problem, separate questions such as:

- Screen: "conversation header with a search button"
- Screen: "conversation search field with cancel control and keyboard"
- Flow: "opening conversation search and returning to the conversation"

These are possible searches, not evidence that such results exist. Translate each user's domain into its own queries rather than reusing chat terminology everywhere.

Start with small batches so every image can be inspected. Increase coverage by changing queries and following promising results, not by flooding context with unexamined hits. Deduplicate screens by ID and flows by ID; prefer distinct interaction patterns over multiple copies of one pattern.

Keep task metadata consistent across calls:

- `output_destination` follows the actual output. Coded sample demos use `code`, even when the package also contains a report.
- Set `output_tool` only when known; keep it consistent. It names the next product, not Mobbin unless results go back into Mobbin.
- `task_intent` is a short English task summary. Do not include verbatim conversation, file contents, or personal data.

## Images and citations

Inspect returned images before describing their content. Flow previews can sample a sequence; examine available screen positions before claiming which states or actions were captured.

Each mentioned screen needs a Markdown citation to its returned `mobbin_url`. Cite flows and sections through their canonical links too. Never manufacture source links or cite a search query as a specific reference.

Inline previews are for agent inspection. For user-facing media, use the host's permitted native gallery or display method. When saving, exporting, or embedding source images into persistent artifacts, use the high-resolution `image_url` rather than the preview, and download only through supported, permitted mechanisms. Image URLs expire after 30 days; persist authorized assets locally and retain the canonical Mobbin link. Do not download media to bypass host display restrictions. If assets cannot be saved or displayed, provide canonical links and report the limitation.

If `search_screens` returns `ai_usage_notice`, reproduce it verbatim as its own block after results, preserving formatting and line breaks.

## Motion and access limits

Flow results currently contain ordered screenshots and action labels, not recordings or motion measurements. Only describe timing, easing, or gesture behavior as observed when you have inspected actual playback or another first-party source establishes it. Cite that evidence separately from the Mobbin stills.

If authentication, permissions, quotas, or unsupported capabilities block a branch, record the gap. Retry only after a changed condition or for a transient failure; do not repeatedly retry unchanged failures. Continue independent work, but disclose incomplete coverage and unfinished outputs. Never substitute fabricated examples.
