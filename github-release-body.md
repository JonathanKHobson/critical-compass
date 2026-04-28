# Critical Compass v0.1.0-beta.9

Beta.9 is the stabilization release after the local beta.8.x train: report validation, clean-render hardening, human-loop guidance, package sync, and public surface cleanup.

## Download Guide

- `critical-compass-plugin.zip`: Claude Cowork and Claude Code plugin upload.
- `critical-compass-0.1.0.mcpb`: Claude Desktop extension install through Settings > Extensions.
- `critical-compass.skill` and `skill.zip`: skill / prompt-only alternative.
- `critical-compass-source.zip`: source files for inspection, modification, or rebuilds.
- `critical-compass-example-report.html` and `critical-compass-example-report.pdf`: redacted public example audit.
- `checksums.txt`: SHA-256 checksums.

## What's New

- `validate_report_payload` dry-runs report payloads before rendering and can return schema docs with `schema_only=true`.
- Advanced synthesis returns a `report_ready_payload` so host AIs have less brittle payload assembly work.
- PDF/HTML reports suppress placeholder/debug strings, raw enum values, and reader-facing internal notes.
- CIS bands and action routing are explicit; low-score reports cannot render `Trust` as the primary action.
- Human-loop guidance now foregrounds `PAUSE_REQUIRED` and Claude's native `Ask_User_Input_V0` style question UI.
- Runtime bundles exclude planning-registry material and do not rely on external MCP orchestration.

Claude's unverified developer/access warning is expected for locally shared plugins and extensions. A Claude Artifact mirror is available at https://claude.ai/public/artifacts/9e50e78b-3877-40c0-855b-07031eb15c95.
