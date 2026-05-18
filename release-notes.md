# Critical Compass 0.1.0-beta.10 Release Notes

This beta.10 release is a delivery-layer hotfix on top of beta.9. It preserves the stabilized package surface while fixing silent-mode consent, report preflight compatibility, and PDF timeout recovery.

- Claude Cowork plugin zip for Claude Cowork and Claude Code.
- Claude Desktop extension file for Claude Desktop Settings > Extensions.
- Skill files for prompt-only alternative use.
- `validate_report_payload` with `schema_only=true` for dry-run diagnostics, schema discovery, renderer status, and field constraints before PDF generation.
- `generate_audit_report(preflight_check=true)` as compatibility sugar for hosts that look for preflight inside the report tool.
- `report_ready_payload` support from advanced synthesis so host AIs fill gaps instead of hand-assembling complex report data from scratch.
- Stable report preflight cards, renderer diagnostics, Markdown-first PDF failure recovery, renderer timeout logging, WeasyPrint/PyMuPDF fallback behavior, and canonical follow-up activity paths.
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
