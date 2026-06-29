# traffic_VLC — Intensidad de tráfico por tramos (València)

Archivo histórico de la **intensidad de tráfico por tramos** de la ciudad de
València, recogida del portal de datos abiertos municipal (hoy descatalogado).

## Origen

- **Fuente:** Ayuntamiento de València — portal *mapas.valencia.es*
  (`lanzadera/opendata/Tra-intensidad-trafico/JSON`).
- El servicio dejó de estar disponible; este repositorio es una copia de
  respaldo del histórico capturado periódicamente.

## Periodo

- **1637 días** entre **17-12-2014** y **24-10-2024**.
- Hay un hueco entre 2017 y 2019 (sin recogida en ese intervalo).

## Estructura del repositorio

- Un fichero ZIP por día: `DD-MM-YYYY.zip`.
- Cada ZIP contiene los JSON capturados ese día (varias lecturas a lo largo
  de la jornada). El nombre original de cada fichero incluye la marca de
  tiempo de la captura.
- Cada commit ("new day") corresponde a un día, fechado con la fecha real
  del dato.

## Formato y campos

Cada JSON es un **GeoJSON `FeatureCollection`** en proyección **EPSG:25830**
(UTM huso 30N, ETRS89). Cada *Feature* es un tramo viario (geometría
`LineString`) con estas propiedades:

| Campo       | Significado                                                        |
|-------------|--------------------------------------------------------------------|
| `idtramo`   | Identificador del tramo viario.                                    |
| `lectura`   | Intensidad de tráfico medida en el tramo. `"-1"` = sin dato.       |
| `des_tramo` | Descripción / denominación del tramo.                              |
