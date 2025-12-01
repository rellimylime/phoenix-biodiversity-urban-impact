# Phoenix Biodiversity Intactness Index Analysis (2017-2020)

## About

This repository contains a geospatial analysis examining changes in the Biodiversity Intactness Index (BII) within the Phoenix subdivision between 2017 and 2020. The analysis quantifies the impact of urban expansion on biodiversity, with Maricopa County identified as the U.S. county experiencing the most significant increase in developed land from 2001 to 2021.

The project calculates the percentage of the Phoenix area maintaining high biodiversity (BII ≥ 0.75) and visualizes spatial patterns of biodiversity loss during this three-year period. This work contributes to understanding how rapid urbanization affects natural ecosystems in one of America's fastest-growing metropolitan areas.

## Repository Structure

```
phoenix-bii-analysis/
│
├── bii_analysis.ipynb       
│
├── data/                            
│     └── tl_2020_04_cousub
│
├── .gitignore                       
└── README.md                        
```

The `bii_analysis.ipynb` contains all data processing, analysis, and visualization code. The `data/` directory is for local copies of shapefiles, though the primary BII raster data is accessed directly from Microsoft Planetary Computer.

## Data

### Data Sources

**Biodiversity Intactness Index (BII) Rasters**  
BII data is accessed programmatically from the Microsoft Planetary Computer STAC catalog (`io-biodiversity` collection). The analysis uses 2017 and 2020 rasters for the Phoenix area (bounding box: -112.826843, 32.974108, -111.184387, 33.863574). No local download is required—data is loaded directly via `pystac_client` and `odc-stac`.

**Phoenix Subdivision Boundary**  
Census county subdivision shapefile for Arizona is required and should be downloaded from the U.S. Census Bureau TIGER/Line shapefiles:
- Download from: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html
- Select year (2020 or later), layer type "County Subdivisions", and state "Arizona"
- Extract and place in the `data/` directory, or update the file path in the notebook

### Running the Analysis

1. Install required Python packages:
```bash
pip install numpy pandas geopandas rioxarray xarray pystac-client planetary-computer odc-stac matplotlib contextily
```

2. Download the Phoenix subdivision shapefile (see above) and update the file path in the notebook

3. Run the Jupyter notebook `bii_analysis.ipynb`

## References

- Microsoft Planetary Computer. (n.d.). *io-biodiversity*. Retrieved from https://planetarycomputer.microsoft.com/dataset/io-biodiversity

- U.S. Census Bureau. (n.d.). *TIGER/Line Shapefiles: County Subdivisions*. Retrieved from https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html

- Developed for EDS 220: Working with Environmental Datasets at UC Santa Barbara's Bren School of Environmental Science & Management, Masters of Environmental Data Science program.

### Additional Resources

[1] Analysis based on findings from: Maricopa County urban development patterns (2001-2021)

[2] Biodiversity Intactness Index methodology: Scholes, R. J., & Biggs, R. (2005). A biodiversity intactness index. *Nature*, 434(7029), 45-49.
