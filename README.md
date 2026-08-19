# London Housing Accessibility and Deprivation

Reproducibility materials for an MSc Urban Spatial Science dissertation at University College London.

This project examines the spatial relationship between completed housing development, public transport accessibility (PTAL), and deprivation across London.

## Repository contents

The analysis is organised into six Jupyter notebooks:

1. `01_build_completion_dataset.ipynb`  
   Cleans and combines Planning London Datahub completion records, geocodes housing records using the ONS Postcode Directory, and assigns PTAL values.

2. `02_exploratory_figures.ipynb`  
   Produces the main descriptive statistics, temporal summaries, and exploratory maps.

3. `03_deprivation_extension.ipynb`  
   Integrates the Index of Multiple Deprivation 2019 data into the housing dataset.

4. `04_additional_robustness_analysis.ipynb`  
   Conducts additional data-quality checks and robustness analyses.

5. `05_msoa_spatial_analysis.ipynb`  
   Aggregates the data to MSOA level and performs correlation analysis, regression analysis, Global Moran’s I, and Local Indicators of Spatial Association analysis.

6. `06_gwr_spatial_nonstationarity.ipynb`  
   examines spatial non-stationarity using Geographically Weighted Regression.

## Software environment

The analysis was developed using Python 3.13.

Install the required Python packages with:

    python -m pip install -r requirements.txt

Then launch Jupyter:

    jupyter lab

## Downloading the large input datasets

Two large source datasets are distributed separately through the GitHub Release:

[Download the large input datasets from Release v1.0.0](https://github.com/ZihanZhang20020809/london-housing-accessibility-dissertation/releases/tag/v1.0.0)

Download the following files:

- `ONSPD_FEB_2026_UK.zip`
- `PTAL_2023_Grid_100mx100m_Data.zip`

Extract the file contained in each ZIP directly into the repository root directory, beside the six Jupyter notebooks.

Do not leave the extracted files inside additional subfolders.

After extraction, the repository should contain:

    london-housing-accessibility-dissertation/
    ├── 01_build_completion_dataset.ipynb
    ├── 02_exploratory_figures.ipynb
    ├── 03_deprivation_extension.ipynb
    ├── 04_additional_robustness_analysis.ipynb
    ├── 05_msoa_spatial_analysis.ipynb
    ├── 06_gwr_spatial_nonstationarity.ipynb
    ├── ONSPD_FEB_2026_UK.csv
    ├── PTAL_2023_Grid_100mx100m_Data.geojson
    ├── ID 2019 for London.xlsx
    ├── London_Boroughs.gpkg
    ├── MSOA_2011_London_gen_MHW.shp
    ├── MSOA_2011_London_gen_MHW.shx
    ├── MSOA_2011_London_gen_MHW.dbf
    ├── MSOA_2011_London_gen_MHW.prj
    ├── New Housing Applications - Completed ... (11 CSV files)
    ├── LSOA_2011_London_gen_MHW.shp
    ├── LSOA_2011_London_gen_MHW.shx
    ├── LSOA_2011_London_gen_MHW.dbf
    ├── LSOA_2011_London_gen_MHW.prj
    └── outputs/

The `outputs` directory will be created automatically when the notebooks are executed.

## Running the analysis

Run the notebooks sequentially:

    01 → 02 → 03 → 04 → 05 → 06

Notebook 01 generates the processed housing datasets required by the later notebooks.

Notebook 05 generates the final MSOA-level spatial dataset required by Notebook 06.

Each notebook should be run from the beginning using:

    Kernel → Restart Kernel and Run All Cells

## Expected initial checks

Notebook 01 should identify:

- 11 Planning London Datahub completion files
- 40,111 combined PLD records
- 26 initial columns

The expected initial combined dataset shape is:

    (40111, 26)

Differences at this stage may indicate that a source file is missing or that a different data version has been used.

## Data sources

The analysis uses data from:

- [Planning London Datahub](https://www.london.gov.uk/programmes-strategies/planning/digital-planning/planning-london-datahub)
- [PTAL Grid 2023](https://www.arcgis.com/home/item.html?id=0646faf45243463aa04ca685e598f471)
- [ONS Postcode Directory, February 2026](https://geoportal.statistics.gov.uk/datasets/3080229224424c9cb53c0b48f5a64d27)
- [Indices of Deprivation for London](https://data.london.gov.uk/dataset/indices-of-deprivation-2l15g)
- London statistical geography boundary datasets

The source datasets remain subject to the licences and attribution requirements of their original providers.

## Outputs

Generated intermediate datasets, summary tables, spatial datasets, and figures are written automatically to:

    outputs/

Figures are written to:

    outputs/figures/

## Author

Zihan Zhang  
MSc Urban Spatial Science  
University College London
