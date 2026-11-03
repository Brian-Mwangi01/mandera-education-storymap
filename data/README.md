# Optional project layers for the interactive map

The interactive map in `index.html` looks for these three files. Each is optional: any file that is
missing is simply skipped, so the map works as a reference map until you add them.

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
