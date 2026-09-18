# Data Notes: Wammakko Health Access Analysis
## Wammakko Ward Boundaries
- Source:GRID3 Nigeria Operational Wards v3.0 (data.grid3.org)
- Format: GeoPackage (`data/raw/wammakko_wards.gpkg`)
- Geometry Type: Polygon
- Feature Count: 11 wards
- Key Fields: `wardname`, `wardcode`, `lganame` (Wamakko), `statename` (Sokoto)
- Processing Note: Filtered from national layer (`Nigeria_-_Ward_Boundaries`) where `lganame = 'Wamakko'`.
  
## Road Network
- Source: OpenStreetMap (via QuickOSM plugin)
- Format: GeoPackage (`data/raw/osm_roads.gpkg`)
- Geometry Type: LineString
- Feature Count: 23965 road networks
- Key Fields: `highway`, `name`, `surface`
- Processing Note: Queried using `highway=*` over Wammakko extent. Associated point geometries (e.g., bus stops, turning circles) were removed to retain only linear transport infrastructure.

## Health Facilities
- Source: OpenStreetMap (via QuickOSM plugin)
- Format: GeoPackage (`data/raw/osm_health_facilities.gpkg`)
- Geometry Type: Point
- Feature Count: 92 Health facilities
- Key Fields: `amenity`, `name`, `healthcare`
- Processing Note: Extracted using `amenity=hospital`, `amenity=clinic`, and `amenity=doctors` within Wammakko extent.

## Settlements
- Source: OpenStreetMap (via QuickOSM plugin)
- Format: GeoPackage (`data/raw/osm_settlements.gpkg`)
- Geometry Type: Point
- Feature Count: 284 settlemts
- Key Fields: `place`, `name`, `population`
- Processing Note: Extracted using `place=*` (villages, towns, hamlets) within Wammakko extent.)

## CRS and Data Preparation
- Source CRS: All raw source layers arrived in unprojected `EPSG:4326` (WGS 84).
- Target Projected CRS: `EPSG:32631` (WGS 84 / UTM Zone 31N) for accurate metric distance and area computations.
- Study Area Extraction: Extracted Wammakko Local Government Area boundary (`study_area.gpkg`) from GRID3 boundary data.
  
## Geoprocessing 
- Clipped all vector datasets (`osm_roads`, `Health_facility`, `Settlements`) to the Wammakko LGA boundary.
- Reprojected all clipped outputs to `EPSG:32631` and saved them into `data/processed/`.
  
## Area Sanity Check: Individual ward area measures ~92.15 km² (with total Wammakko LGA summing to ~1,290 km²), confirming accurate reprojection from square degrees to square kilometers.

## Directory Structure: Unmodified raw layers remain intact in `data/raw/`; all analysis-ready layers are stored in `data/processed/`.
