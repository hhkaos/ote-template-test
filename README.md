# OTE Template

Fork this repository and get, with nothing but GitHub and GitHub Pages:

- Your community's **[OTE](https://opentechevents.org) event feed** published at a public URL.
- **iCalendar (`events.ics`)** and **RSS (`feed.xml`)** exports, rebuilt automatically on every change.
- A minimal **dashboard** linking to the central OTE tools (editor, import, publish).

Your data stays in **your** repository, as plain JSON, under an open license.
No lock-in: the ICS/RSS exports mean you can leave anytime and take everything with you.

## What's in this repo

```
├── events/*.json          ← your events (one file per event)
├── ote.config.json        ← your configuration (feed title, description…)
├── docs/index.html        ← static dashboard (links to central tools)
└── .github/workflows/     ← thin workflows calling reusable workflows
                             in OpenTechEvents/ote-tools
```

That's all. Validation, exports and the editor UI live in
[OpenTechEvents/ote-tools](https://github.com/OpenTechEvents/ote-tools) and are
consumed via reusable workflows — improvements reach your fork without you
touching anything.

## Get started

### 1. Fork

Click **Fork** on this repository. Fork — not "Use this template" — so you can
later pull upstream improvements to the dashboard and workflows:

```
git remote add upstream https://github.com/OpenTechEvents/ote-template
git pull upstream main
```

### 2. Enable GitHub Pages

In your fork: **Settings → Pages → Source: GitHub Actions**.

### 3. Edit `ote.config.json`

Set your feed's `title`, `description` and `url` (your community's website).
Keep or change the `license` (it applies to your event *data*).

### 4. Replace the sample events

Delete the files in [events/](events/) and add your own — one JSON file per
event. Use the samples as a starting point; the full field reference is at
[opentechevents.org/spec](https://opentechevents.org/spec/). Minimal event:

```json
{
  "specVersion": "0.2.0",
  "id": "https://your-community.example/events/2026-09-meetup",
  "name": "September meetup",
  "startDate": "2026-09-24T19:00:00",
  "timezone": "Europe/Madrid",
  "license": "CC-BY-4.0"
}
```

File names are free-form — any `*.json` under `events/` is picked up. The
samples use `YYYY-MM-name.json` so files sort chronologically, but nothing
depends on it: an event's identity is its `id` field, not its file name.

Every push validates your events and, if valid, rebuilds and redeploys your
site: dashboard + `feed.json` + `events.ics` + `feed.xml` at
`https://<user>.github.io/<repo>/`. Deploys take a couple of minutes.

### 5. Make your feed discoverable

Add this to the `<head>` of your community's website (if you have one):

```html
<link rel="alternate" type="application/ote+json"
      href="https://<user>.github.io/<repo>/feed.json">
```

### 6. Register as an adopter

Add your community to the adopters list in
[opentechevents-spec](https://github.com/OpenTechEvents/opentechevents-spec) so
directories and users can find your feed.

## Editing events

Phase 1 is hand-edited JSON — the workflows validate every push and pull
request, so mistakes can't reach your published feed. The **editor** linked
from your dashboard (create/edit events via a form, proposed as a PR to your
repo) is coming in phase 2.

## Updates

The thin workflows track `OpenTechEvents/ote-tools@main` (pinned to `@v1` once
stable), so validation and export improvements arrive automatically. For the
few files that live here (dashboard, workflows), pull from upstream now and
then:

```
git pull upstream main
```

## License

Sample events and configuration: [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).
Your own data: whatever `license` you declare in `ote.config.json` and your events.
