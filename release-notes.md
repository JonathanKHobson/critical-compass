# Critical Compass 0.1.0-beta.9 Release Notes

This beta.9 release is a stabilization release. It freezes new feature work, syncs the public package surface with the current local MCP, and hardens the report path so host AIs can validate payloads before rendering.

- Claude Cowork plugin zip for Claude Cowork and Claude Code.
- Claude Desktop extension file for Claude Desktop Settings > Extensions.
- Skill files for prompt-only alternative use.
- `validate_report_payload` with `schema_only=true` for dry-run diagnostics, schema discovery, renderer status, and field constraints before PDF generation.
- `report_ready_payload` support from advanced synthesis so host AIs fill gaps instead of hand-assembling complex report data from scratch.
- Stable report preflight cards, renderer diagnostics, WeasyPrint/PyMuPDF fallback behavior, and canonical follow-up activity paths.
- Natural-key normalization for common host payloads such as `cis_score`, `bias_rows`, and `bias`.
- Explicit CIS bands and safer action routing so low-scoring reports do not render `Trust` as the primary action.
- Human-loop guidance that highlights `PAUSE_REQUIRED` and asks Claude hosts to use native `Ask_User_Input_V0` / conversational UI widgets.
- Teaching-layer outputs: plain-language read, before-use caution, solo/group follow-up activities, and Critical Compass activity attribution.
- Planning-leak cleanup: no external MCP orchestration, no third-party MCP dependency map, and no planning-registry material in runtime bundles.
- Reader-facing report cleanup for placeholder/debug strings, raw enum values, empty sections, and KB-grounding internals.
- Refreshed standalone Critical Compass skill references.
- Redacted public example audit in HTML, PDF, and Markdown.
- Source zip for technical reviewers who want to inspect or rebuild the project.
- AI-assisted install prompt for technical local MCP source installs.
- Diagnostics prompt for install troubleshooting.
- Checksums for all downloadable artifacts.

Critical Compass runs locally and does not orchestrate other MCPs. Fact-checking remains scaffold-first by default. No Google, Brave, provider key, runtime external-archive dependency, or separate activity database is required.
