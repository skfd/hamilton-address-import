# hamilton-address-import

The **Hamilton city checkout** of the address-import family — city #2,
decided 2026-08-13. Status: **onboarding**. No proposal published, no uploads
made; the config here is a first draft for conflation baseline runs.

The pipeline lives in the engine repo,
[`address-importer-friend`](https://github.com/skfd/address-importer-friend)
(see its README for setup). This repo carries only Hamilton's `config.toml`,
credentials (`.env.*`, gitignored, from the `.example` files), and — locally,
gitignored — `data/` with the OSM extract and `data/hamilton/tool.db`.

```bash
cd ../address-importer-friend
python run.py --city-dir ../hamilton-address-import
```

Source data: City of Hamilton address points, consumed via the sibling
[`ontario-address-changes`](https://github.com/skfd/ontario-address-changes)
tracker (`data/hamilton/hamilton.db`, 273k address rows as of 2026-08-13).

Before any production upload: entry-state survey confirmed greenfield
(2026-08-12 portfolio survey), but the import still needs its own wiki
proposal page, forum announcement, and feedback window per the
[OSM Import Guidelines](https://wiki.openstreetmap.org/wiki/Import/Guidelines)
— Toronto's [`IMPORT_PROPOSAL.mediawiki`](https://github.com/skfd/toronto-2-address-import/blob/main/IMPORT_PROPOSAL.mediawiki)
is the template. Hamilton defers no unit addresses, so the units question
(engine `future-work/multi-city/09-units.md`) does not block it.

MIT licensed.
