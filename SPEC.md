## `water`
### Contents
Polygonal water bodies.
- zoom 0 to 4, natural earth ocean + lake
- zoom 5 to 9, osm simplified_ocean_polygons
- zoom 10+, osm ocean_polygons
- zoom 5+  OSM waterway=riverbank or landuse=reservoir or natural=water

Minimum size of 0.25 pixels for OSM-sourced data

Buffer of 4 pixels

### Fields
- `water`: `ocean`, `lake`, `river`, `reservoir`, or value of OSM `water` tag
### Ordering
None

## `water_names`
### Contents
Points with water names.  
Sources as with `water` layer, except sources without name data can be ignored.

Minimum size of 16 pixels for OSM-sourced data

Buffer of 128 pixels

### Fields
- `name`: name of water body
- `water`: `ocean`, `lake`, `river`, `reservoir`, or value of OSM `water` tag
### Ordering
By size then name as text

## `transport`
### Contents
Transportation linear features.  
All from OSM data, with features appearing at the following zooms
* `motorway`: z6
* `trunk`: z7
* `primary`: z8
* `secondary`: z9
* `tertiary`: z10
* `residential`, `unclassified`: z12
* `service`, `track`, and non-motorized types: z14
`_link` roads of any type not shown until z10

Rail features not included for now.

If the feature is oneway, then the direction of it is the direction of travel.

Buffer of 128 pixels

### Fields
- `name`: Name of road
- `ref`: Reference of road
- `class`: value of `highway` tag, excluding `_link`
- `link`: True if the feature is a `_link`, empty otherwise
- `oneway`: True if oneway=true or reverse, starts at z10
- `brunnel`: `tunnel` or `bridge` for tunnels or bridges, with bridge taking priority

### Ordering
By layer with highest layer first, ramp with ramps first, class with most significant first, then name
