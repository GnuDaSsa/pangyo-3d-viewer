# Regional road data

`regional-roads.osm.json` contains a clipped and coordinate-transformed extract of OpenStreetMap road centreline data, obtained on 2026-09-09 through Overpass API. It is attributed to **OpenStreetMap contributors** and is available under the **Open Database License (ODbL) 1.0**.

- Attribution: https://www.openstreetmap.org/copyright
- License: https://opendatacommons.org/licenses/odbl/1-0/
- Query: ways classified as motorway, trunk, primary, secondary, tertiary, residential or unclassified, including link roads, within 1,100m of 37.40903,127.09484. Tunnel/private/no-access ways are omitted.
- Transform: the registration recorded inside the JSON maps geographic coordinates to the prototype's estimated local origin. Widths are illustrative by road category; they are not surveyed widths. The JSON records OSM way identifiers and extraction timestamp.
- Reproduction: `scripts/build-regional-roads.py` consumes an Overpass response at `output/wide-roads-osm.json` and the previously collected GBIS line response. The original response can be fetched again using the documented query; no tile images are used.

`regional-connectors.gbis.json` separately contains short, transformed GBIS Nuri2 line samples at the existing road display boundary. Its source is https://www.gbis.go.kr/gbis2014/schBusAPI.action (`searchMapLineJson`, routeId 204000146). Its widths and local registration are estimates; see `analysis/bus-research.md`.

Kakao Map was viewed only to compare surrounding road names and connections. No Kakao SDK, tiles, map imagery, or traced Kakao vector dataset is distributed. The ODbL notice above concerns the OSM-derived dataset; it does not relicense the application source code or user-supplied architectural documents.
