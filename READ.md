# Human Modification Atlas

A geospatial data exploration project investigating the spatial distribution of human modification across Earth's terrestrial surface.

The project uses the Global Human Modification dataset to explore how human pressure is distributed geographically, while serving as a practical introduction to raster GIS workflows in Python.

## Project Status

🚧 Work in progress

The current implementation focuses on raster data auditing and regional exploration. A global interactive visualization and comparative regional analysis will be developed in later stages.

## Current Features

- Inspection of large GeoTIFF raster metadata with Rasterio
- CRS, resolution, bounds, transforms, and NoData analysis
- Memory-safe windowed raster reading
- Geographic coordinate-to-pixel conversion
- Remote access to a ~9 GB Cloud-Optimized GeoTIFF (COG)
- Analysis of the `NS` (Natural System Modification) layer
- Analysis of the `AA` (All Threats Combined) layer
- Human Modification classification into:
  - Very low
  - Low
  - Moderate
  - High
  - Very high
- Initial regional analysis over a central Germany sample window

## Dataset

Global Human Modification (gHM), The Nature Conservancy. Cite all versions DOI: https://doi.org/10.5281/zenodo.14502573 

The primary analysis uses the 2022 static 300 m `AA` (All Threats Combined) Cloud-Optimized GeoTIFF.

Large source rasters are not stored in this repository. They are accessed from the original public data source or ignored locally through `.gitignore`.

## Tech Stack

- Python
- NumPy
- pandas
- Rasterio
- rioxarray
- xarray
- GeoPandas
- Matplotlib
- PyDeck

## Repository Structure

```text
human-modification-atlas/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   └── 01_data_audit.ipynb
├── outputs/
│   ├── figures/
│   └── maps/
├── .gitignore
├── environment.yml
└── README.md
```

## Next Steps 

The next stages will expand the analysis from regional raster samples toward global and cross-regional comparisons, followed by an interactive geospatial visualization.

The goal is to investigate the data first and let the final visual story emerge from the analysis rather than starting from a predetermined conclusion.

