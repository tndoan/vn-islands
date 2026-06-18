## Paracel & Spratly Islands Map

Static GitHub Pages site for an interactive map of notable Paracel Islands
and Spratly Islands features.

### What is included

- Leaflet map using real latitude/longitude coordinates.
- Island data stored separately in `islands.json`.
- Hover/tap tooltips for island or reef overview.
- Filters for archipelago and de facto administrator/occupier.
- Search by feature name, local name, type, or administrator.
- Detail panel with area, de facto administrator, claimants, and reference link.

### Run locally

Serve the folder:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

Opening `index.html` directly from the filesystem is not recommended because
the browser may block loading `islands.json`.

### Data File

`islands.json` is the source of truth for map data. It is a list where each
element represents one island, cay, reef, or artificial-island feature.

Each element includes:

- `name`, `localNames`, `archipelago`, and `featureType`
- `area.naturalHa` and optional `area.reclaimedHa`
- `location.center` with `lat` and `lng`
- `location.shape`, currently stored as an approximate point placeholder until
  precise coastline polygons are traced
- `deFactoAdministrator`
- `claimants`
- `summary`
- `sources`

### Deploy to GitHub Pages

For a project page at `<myname>.github.io/vn-islands`:

1. Push this repository to GitHub as `vn-islands`.
2. In GitHub, open repository `Settings` -> `Pages`.
3. Set `Source` to `Deploy from a branch`.
4. Select the branch and root folder, then save.

All asset paths are relative, so the site works under `/vn-islands/`.

### Data Notes

The South China Sea disputes are politically sensitive. This project uses
"de facto administrator/occupier" for current control and lists sovereignty
claims separately. Coordinates and areas are approximate and should be verified
before using this as an authoritative reference.

Primary public references used while building the initial dataset:

- Paracel Islands overview:
  https://en.wikipedia.org/wiki/Paracel_Islands
- Woody Island:
  https://en.wikipedia.org/wiki/Woody_Island_(South_China_Sea)
- Pattle Island:
  https://en.wikipedia.org/wiki/Pattle_Island
- Spratly Islands overview:
  https://en.wikipedia.org/wiki/Spratly_Islands
- Spratly maritime features list:
  https://en.wikipedia.org/wiki/List_of_maritime_features_in_the_Spratly_Islands
- Thitu Island:
  https://en.wikipedia.org/wiki/Thitu_Island
- Northeast Cay:
  https://en.wikipedia.org/wiki/Northeast_Cay
- Southwest Cay:
  https://en.wikipedia.org/wiki/Southwest_Cay
- Spratly Island:
  https://en.wikipedia.org/wiki/Spratly_Island
- AMTI island tracker examples for reclaimed reefs:
  https://amti.csis.org/
