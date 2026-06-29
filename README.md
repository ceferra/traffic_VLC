# traffic_VLC — Traffic intensity by road segment (València)

Historical archive of **traffic intensity by road segment** for the city of
València, collected from the municipal open-data portal (now decommissioned).

## Source

- **Publisher:** València City Council — *mapas.valencia.es* portal
  (`lanzadera/opendata/Tra-intensidad-trafico/JSON`).
- The service is no longer available; this repository is a backup copy of the
  history captured periodically.

## Period

- **1637 days** between **2014-12-17** and **2024-10-24**.
- There is a gap between 2017 and 2019 (no collection during that interval).

## Repository layout

- One ZIP file per day: `DD-MM-YYYY.zip`.
- Each ZIP holds the JSON snapshots captured that day (several readings
  throughout the day). The original file name embeds the capture timestamp.
- Each commit ("new day") corresponds to one day, dated with the real date of
  the data.

## Format and fields

Each JSON is a **GeoJSON `FeatureCollection`** in projection **EPSG:25830**
(UTM zone 30N, ETRS89). Each *Feature* is a road segment (`LineString`
geometry) with these properties:

| Field       | Meaning                                                            |
|-------------|--------------------------------------------------------------------|
| `idtramo`   | Road-segment identifier.                                           |
| `lectura`   | Measured traffic intensity on the segment. `"-1"` = no data.       |
| `des_tramo` | Segment description / name.                                        |
