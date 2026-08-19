# Guatemala Administrative Divisions / Guatemala



## Overview

| Item | Details |
|------|---------|
| Department | 22 |
| Municipality | 342 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/gt](https://openadmindata.org/gt/) |
| API | [openadmindata.org/api/gt](https://openadmindata.org/api/gt/) |
| National Anthem | [🎵 Listen & Download Guatemala National Anthem MP3](https://onlygames.me/national-anthems/gt/) |

## Browse by Department

| # | Department | Municipalitys | Link |
|---|----|----|------|
| 1 | Alta Verapaz | 17 | [Browse](divisions/alta-verapaz-gt16/) |
| 2 | Baja Verapaz | 8 | [Browse](divisions/baja-verapaz-gt15/) |
| 3 | Chimaltenango | 16 | [Browse](divisions/chimaltenango-gt04/) |
| 4 | Chiquimula | 11 | [Browse](divisions/chiquimula-gt20/) |
| 5 | El Progreso | 8 | [Browse](divisions/el-progreso-gt02/) |
| 6 | Escuintla | 14 | [Browse](divisions/escuintla-gt05/) |
| 7 | Guatemala | 18 | [Browse](divisions/guatemala-gt01/) |
| 8 | Huehuetenango | 33 | [Browse](divisions/huehuetenango-gt13/) |
| 9 | Izabal | 5 | [Browse](divisions/izabal-gt18/) |
| 10 | Jalapa | 7 | [Browse](divisions/jalapa-gt21/) |
| 11 | Jutiapa | 17 | [Browse](divisions/jutiapa-gt22/) |
| 12 | Petén (Peten) | 14 | [Browse](divisions/peten-gt17/) |
| 13 | Quetzaltenango | 24 | [Browse](divisions/quetzaltenango-gt09/) |
| 14 | Quiché (Quiche) | 21 | [Browse](divisions/quiche-gt14/) |
| 15 | Retalhuleu | 9 | [Browse](divisions/retalhuleu-gt11/) |
| 16 | Sacatepéquez (Sacatepequez) | 16 | [Browse](divisions/sacatepequez-gt03/) |
| 17 | San Marcos | 30 | [Browse](divisions/san-marcos-gt12/) |
| 18 | Santa Rosa | 14 | [Browse](divisions/santa-rosa-gt06/) |
| 19 | Sololá (Solola) | 20 | [Browse](divisions/solola-gt07/) |
| 20 | Suchitepéquez (Suchitepequez) | 21 | [Browse](divisions/suchitepequez-gt10/) |
| 21 | Totonicapán (Totonicapan) | 8 | [Browse](divisions/totonicapan-gt08/) |
| 22 | Zacapa | 11 | [Browse](divisions/zacapa-gt19/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-department.json](data/all-department.json) | JSON | All 22 department records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 342 municipality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-department.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['municipality']} municipalitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-department.json", "utf-8"));
console.log(`Total: ${data.length} departments`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=department, 2=municipality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{department-slug}/
```

Municipalitys are listed inline in each department's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-department links
- [Per-department data](docs/llms-full/) — Full data by department

## Citation

```
Guatemala Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/guatemala-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
