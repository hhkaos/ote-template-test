# Changelog

Notable changes to the OTE template — the files that live in *your* fork
(dashboard, thin workflows, issue templates, docs). Improvements to validation
and exports arrive automatically via `OpenTechEvents/ote-tools` and are **not**
tracked here.

This file, together with the [`VERSION`](VERSION) marker, is what the dashboard
reads to tell you a newer template is available and what it changed. To pull an
update in: `git pull upstream main` (see the README's *Updates* section).

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/);
versions follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2026-07-17

Phase 1 (MVP): fork → configure three values → a validated OTE feed with ICS/RSS
exports published on GitHub Pages.

### Added
- Thin workflows calling `ote-tools` reusable workflows: validate, publish
  (build Pages), and issue-to-PR.
- Static dashboard (`docs/index.html`) linking to the central tools, with the
  adopter-registry banner.
- `propose-event` issue form and the `ote-event` label contract.
- `ote.config.json`, sample events, `CONTRIBUTING.md`, and the setup guide.
- `VERSION` + this changelog, so the dashboard can surface template updates
  client-side.
