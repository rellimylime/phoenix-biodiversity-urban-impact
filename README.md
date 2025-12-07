# Biodiversity Intactness Index Change in Phoenix, Arizona (2017-2020)

## About

This repository contains a Jupyter notebook that analyzes changes in the Biodiversity Intactness Index (BII) within the Phoenix subdivision between 2017 and 2020. The analysis quantifies the impact of urban expansion on biodiversity, focusing on areas where BII values declined during this period. Maricopa County experienced the largest increase in developed land among U.S. counties between 2001 and 2021, making this analysis critical for understanding urbanization's ecological impact.

**Key outputs:**
- Percentage of area maintaining high biodiversity (BII ≥ 0.75) in 2017 and 2020
- Spatial visualization of biodiversity loss at preserve boundaries
- Identification of protected areas maintaining high BII values

This project was completed as part of EDS 220: Working with Environmental Datasets at the Bren School of Environmental Science & Management, UC Santa Barbara.

## Repository Structure

```
phoenix-bii-analysis/
│
├── README.md
├── bii_analysis.ipynb
├── .gitignore
│
└── data/
    └── tl_2020_04_cousub/
```

## Data

### Data Sources

**Biodiversity Intactness Index (BII) Time Series**  
The BII measures the average abundance of naturally occurring species relative to their abundance in undisturbed ecosystems. Values range from 0 to 1, with 1 representing intact biodiversity. This analysis uses BII rasters for 2017 and 2020 from the Microsoft Planetary Computer's io-biodiversity collection, covering the Phoenix subdivision area (bounding box: -112.826843, 32.974108, -111.184387, 33.863574). The data is accessed programmatically via the STAC API and does not require manual download.

**Phoenix Subdivision Shapefile**  
Census county subdivision boundary for Phoenix from the U.S. Census Bureau's TIGER/Line shapefiles, used to define the study area and clip raster data. This shapefile delineates the Phoenix Census County Division (CCD) boundary as of 2020.

### Data Access

**BII Rasters:**  
The BII data is **not included** in this repository. It is accessed directly from the Microsoft Planetary Computer STAC catalog during notebook execution using `pystac_client` and `odc-stac`. No manual download is required.

**Phoenix Subdivision Shapefile:**  
The shapefile is **not included** in this repository. Download the Census county subdivision shapefile for Arizona:
1. Visit: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html
2. Select year (2020 or later), layer type "County Subdivisions", and state "Arizona"
3. Download and extract to the `data/` directory

**Note:** The shapefile must be downloaded separately to reproduce the analysis.

## Requirements

This analysis requires Python 3.x with the following packages:
- `numpy` - Numerical operations and array masking
- `geopandas` - Vector geospatial data handling (shapefiles)
- `rioxarray` - Geospatial raster data operations
- `pystac-client` - STAC catalog access
- `planetary-computer` - Microsoft Planetary Computer authentication
- `matplotlib` - Data visualization
- `contextily` - Basemap integration

Install all dependencies:
```bash
pip install numpy geopandas rioxarray pystac-client planetary-computer matplotlib contextily
```

## References

City of Phoenix Parks and Recreation Department. (n.d.). South Mountain Park/Preserve. https://www.phoenix.gov/parks/trails/locations/south-mountain

City of Scottsdale. (n.d.). McDowell Sonoran Preserve. https://www.scottsdaleaz.gov/preserve

Galaz García, C., Cawse-Nicholson, K., Frew, A., & Fontenot, R. (2024). EDS 220: Working with environmental datasets [Course materials]. Master of Environmental Data Science, Bren School of Environmental Science & Management, University of California, Santa Barbara. https://meds-eds-220.github.io/MEDS-eds-220-course/

Maricopa County Parks and Recreation. (n.d.). McDowell Mountain Regional Park. https://www.maricopacountyparks.net/park-locator/mcdowell-mountain-regional-park/

Microsoft Planetary Computer. (n.d.). io-biodiversity [Dataset]. https://planetarycomputer.microsoft.com/dataset/io-biodiversity

Scholes, R. J., & Biggs, R. (2005). A biodiversity intactness index. Nature, 434(7029), 45-49. https://doi.org/10.1038/434045a

U.S. Census Bureau. (n.d.). TIGER/Line Shapefiles: County Subdivisions [Dataset]. https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html

## License

This project is licensed under the terms included in the LICENSE file.

---

*This project is part of the curriculum for the Master of Environmental Data Science program at the Bren School of Environmental Science & Management, UC Santa Barbara.*