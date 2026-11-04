# Project layers for the interactive map

The interactive map in `index.html` looks for these three files. `primary-schools.geojson` is included (converted
from the project's `Primary School` KML layer: 151 records, attributes limited to name, code, level, status, subcounty,
ward and source). `mandera-county.geojson` and `mandera-subcounties.geojson` are Mandera extracts of the GADM version 2.8 Kenya boundaries (simplified
for the web; the 7 units are GADM's constituency-level units, including the one GADM labels `?1`). A missing file is simply skipped.

**Licence note:** GADM 2.8 is licensed for non-commercial use and its licence says the data may not be redistributed without
prior consent. Publishing these two files on GitHub Pages is a form of redistribution, so confirm that this is acceptable for
your use, or delete both files (the map then shows schools without boundaries).

| File | Geometry | Used for |
|------|----------|----------|
| `mandera-county.geojson` | Polygon / MultiPolygon | County outline (map zooms to it) |
| `mandera-subcounties.geojson` | Polygon / MultiPolygon | Subcounty boundaries with name tooltips |
| `primary-schools.geojson` | Point | School points with click-for-details popups |

## Requirements

- GeoJSON in **WGS 84 (EPSG:4326)**, longitude/latitude. The project is in UTM zone 37N (EPSG:32637), so
  reproject before exporting.
- Keep only attributes you are happy to publish. Popups read, if present, a school name from `school_name`,
  `name`, `school` or `facility_name`, and a subcounty from `subcounty`, `sub_county` or `ward`
  (case-insensitive). Subcounty polygons use `subcounty`, `sub_county`, `name` or `subcounty_name` for tooltips.
- Keep files small (simplify boundaries if they are large).

## Exporting

**ArcGIS Pro:** Project the layer to WGS 1984 (Project tool), then *Conversion Tools > JSON > Features To JSON*
with *Output to GeoJSON* ticked.
**QGIS:** Right-click the layer > Export > Save Features As > GeoJSON, CRS EPSG:4326.

Add the original source and provider of the boundary and school datasets to the "Sources" list in `index.html`
once confirmed.
