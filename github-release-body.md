# Critical Compass v0.1.0-beta.10

Beta.10 is a delivery-layer hotfix on top of beta.9: silent-mode consent now honors Claude's flat confirmation state, report preflight is available directly from `generate_audit_report(preflight_check=true)`, and PDF render/QA failures now return the Markdown artifact plus a local error log instead of dropping the deliverable.

## Download Guide

- `critical-compass-plugin.zip`: Claude Cowork and Claude Code plugin upload.
- `critical-compass-0.1.0.mcpb`: Claude Desktop extension install through Settings > Extensions.
- `critical-compass.skill` and `skill.zip`: skill / prompt-only alternative.
- `critical-compass-source.zip`: source files for inspection, modification, or rebuilds.
- `critical-compass-example-report.html` and `critical-compass-example-report.pdf`: redacted public example audit.
- `checksums.txt`: SHA-256 checksums.

## What's New

- `validate_report_payload` dry-runs report payloads before rendering and can return schema docs with `schema_only=true`.
- `generate_audit_report(preflight_check=true)` runs the same dry-run checks without writing files.
- Advanced synthesis returns a `report_ready_payload` so host AIs have less brittle payload assembly work.
- Advanced synthesis confirms accepted silent mode with `human_loop_confirmation`.
- Markdown is written before PDF rendering; renderer or QA timeout failures preserve `markdown_path`, `markdown_hash`, and `render_error_log_path`.
- PDF/HTML reports suppress placeholder/debug strings, raw enum values, and reader-facing internal notes.
- CIS bands and action routing are explicit; low-score reports cannot render `Trust` as the primary action.
- Human-loop guidance now foregrounds `PAUSE_REQUIRED` and Claude's native `Ask_User_Input_V0` style question UI.
- Runtime bundles exclude planning-registry material and do not rely on external MCP orchestration.

Claude's unverified developer/access warning is expected for locally shared plugins and extensions. A Claude Artifact mirror is available at https://claude.ai/public/artifacts/9e50e78b-3877-40c0-855b-07031eb15c95.
