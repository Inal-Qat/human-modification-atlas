# Human Modification Atlas

A geospatial data exploration project investigating the spatial distribution of human modification across Earth's terrestrial surface.

The project uses the Global Human Modification dataset to explore how human pressure is distributed geographically, while serving as a practical introduction to raster GIS workflows in Python.

## Project Status

🚧 Work in progress

The project has progressed from local and regional raster auditing to global-scale exploration of the 2022 Human Modification raster.

The current implementation includes remote Cloud-Optimized GeoTIFF access, overview-aware global downsampling, and experiments comparing resampling strategies for efficient whole-Earth visualization.

The next phase focuses on explicit missing-value handling, global area-weighted analysis, and interactive visualization.

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
- Global-scale downsampling of the ~9 GB `AA` raster without downloading the full dataset
- Inspection and use of COG overview pyramids (`2×`, `4×`, `8×`, `16×`, `32×`)
- Comparison of manually selected 2:1 global display grids with overview-derived resolutions
- Nearest-neighbour vs. average resampling experiments
- Analysis of `NaN` propagation and missing-value behavior during raster resampling
- Memory-efficient global raster representation (~32–33 MB in memory)

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

- Implement NaN-aware global resampling
- Calculate rigorous global Human Modification distributions
- Account for unequal pixel area in EPSG:4326 through area weighting
- Compare modification patterns across selected world regions
- Build an interactive global visualization with PyDeck
- Produce a polished final visualization suitable for portfolio and LinkedIn use

The project continues to follow an exploratory approach: methodological decisions are tested against the data rather than chosen only for visual appearance.

