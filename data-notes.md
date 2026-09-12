[data.notes.md.txt](https://github.com/user-attachments/files/32146668/data.notes.md.txt)[Uploading data.notes.md.txt…](Data Notes — Wammakko Health Access Analysis

1. Wammakko Ward Boundaries
- Source:GRID3 Nigeria Operational Wards v3.0 (data.grid3.org)
- Format: GeoPackage (`data/raw/wammakko_wards.gpkg`)
- Geometry Type: Polygon
- Feature Count: 11 wards
- Key Fields: `wardname`, `wardcode`, `lganame` (Wamakko), `statename` (Sokoto)
- Processing Note: Filtered from national layer (`Nigeria_-_Ward_Boundaries`) where `lganame = 'Wamakko'`.

2. Road Network
- Source: OpenStreetMap (via QuickOSM plugin)
- Format: GeoPackage (`data/raw/osm_roads.gpkg`)
- Geometry Type: LineString
- Feature Count: 23965 road networks
- Key Fields: `highway`, `name`, `surface`
- Processing Note: Queried using `highway=*` over Wammakko extent. Associated point geometries (e.g., bus stops, turning circles) were removed to retain only linear transport infrastructure.

3. Health Facilities
- Source: OpenStreetMap (via QuickOSM plugin)
- Format: GeoPackage (`data/raw/osm_health_facilities.gpkg`)
- Geometry Type: Point
- Feature Count: 92 Health facilities
- Key Fields: `amenity`, `name`, `healthcare`
- Processing Note: Extracted using `amenity=hospital`, `amenity=clinic`, and `amenity=doctors` within Wammakko extent.

4. Settlements
- Source: OpenStreetMap (via QuickOSM plugin)
- Format: GeoPackage (`data/raw/osm_settlements.gpkg`)
- Geometry Type: Point
- Feature Count: 284 settlemts
- Key Fields: `place`, `name`, `population`
- Processing Note: Extracted using `place=*` (villages, towns, hamlets) within Wammakko extent.)
