# Data

This directory holds the input datasets for the analysis. **Its contents are git-ignored**
(only this README is tracked) because the full dataset is ~1.3 GB and several files exceed
GitHub's 100 MB per-file limit. Everything here is reproducible from the sources below.

## How to get the data

The lesson dataset is bundled on Figshare (article **25721754**, ~678 MB). From the repository
root:

```bash
curl -L -o data/rhodes.zip "https://figshare.com/ndownloader/articles/25721754/versions/3"
unzip data/rhodes.zip -d data/
rm data/rhodes.zip
```

## Expected layout after extraction

```
data/
├── sentinel2/     # Sentinel-2 bands (GeoTIFF), Rhodes, 2023-08-27 (+ metadata, thumbnail)
├── dem/
│   └── rhodes_dem.tif        # Copernicus GLO-30 DEM, cropped/mosaicked for the lesson
├── gadm/
│   └── ADM_ADM_3.gpkg        # GADM administrative boundaries (modified for teaching)
└── osm/
    ├── osm_landuse.gpkg      # OpenStreetMap land-use polygons (via Geofabrik)
    └── osm_roads.gpkg        # OpenStreetMap roads (via Geofabrik)
```

## Data sources & credit

- **Sentinel-2 L2A** imagery — ESA / Copernicus, accessed via
  [Earth Search on AWS](https://earth-search.aws.element84.com/v1).
- **DEM** — Copernicus GLO-30.
- **Administrative boundaries** — [GADM](https://gadm.org/).
- **Roads & land use** — [OpenStreetMap](https://www.openstreetmap.org/) contributors, via Geofabrik.

Bundled for the Carpentries Incubator lesson
[Introduction to Geospatial Raster and Vector Data with Python](https://carpentries-incubator.github.io/geospatial-python/).

Some rasters (e.g. `outputs/red.tif`) are additionally produced by running the notebooks,
which pull Sentinel-2 assets directly from the STAC catalog — see [`../outputs/README.md`](../outputs/README.md).
