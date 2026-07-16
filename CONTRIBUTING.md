# Contributing

Thanks for helping keep this community's event feed accurate!

> **Organiser:** this file is a template. Adapt it to your community —
> or delete it (and disable Issues) if you don't want contributions.

## Report a mistake or propose an event

- **Open an issue** describing the event or the error — a maintainer will
  apply it. If you can, include the event as JSON (see the
  [field reference](https://opentechevents.org/spec/)).
- **Or open a pull request** editing the JSON files in [events/](events/)
  directly: one file per event, any file name.

Every pull request is validated automatically against the OTE spec, so you
can't break the published feed — if validation passes and a maintainer
merges, the site (feed, ICS, RSS) redeploys itself.

## License

Event data in this repository is published under the license declared in
[ote.config.json](ote.config.json). By contributing, you agree your
contribution is published under it.
