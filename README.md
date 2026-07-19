# retrace-poi-packs

Venue (point-of-interest) data packs for [Retrace](https://github.com/thekenyeung/retrace),
the local-first photo finder. This repo is public so the Retrace app can download packs
anonymously; it contains only open, redistributable place data — no application source.

Each `poi-<region>.db` is a small SQLite file of **notable venues** for one region
(convention centers, stadiums, airports, museums, parks, landmarks, …), used to label a
photo by name ("Austin Convention Center") instead of a coordinate. `manifest.json` is the
catalog the app reads. Retrace imports a pack on install and searches it fully offline.

## Data source & license

Places © [Overture Maps Foundation](https://overturemaps.org/), used under the
**CDLA Permissive 2.0** license. Packs are derived (filtered to notable venues and cut by
region) from Overture's monthly Places release.

## How packs are built

By the pipeline in the main Retrace repo (`scripts/poi/`), which slices the Overture
Places dataset per region and applies the notable-venue filter. See
`docs/POI-region-packs.md` there for the full spec.
