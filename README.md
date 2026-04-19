# Clustering Solar Energy Production Zones
## New York State — Machine Learning Project

Identifying high-potential solar energy regions through 
unsupervised machine learning clustering analysis.

## Overview
Analysed 218,115 solar project records across 62 New York 
State counties (2000–2023) to cluster geographical areas by 
energy production — enabling strategic business targeting 
and data-driven zone classification.

## Dataset
- 218,115 solar projects
- 17 columns
- 62 New York State counties
- Time period: 2000 to 2023
- Source: NY State Statewide Solar Projects

## Preprocessing
**Data Cleaning**
Handled 214,024 missing storage values, 85,234 missing 
division values, created missing flags before filling nulls, 
standardised city names, and extracted year from date column.

## **Exploratory Data Analysis**
10 visualisations covering energy distribution, top counties, 
yearly growth trend, utility analysis, developer analysis, 
PV system size vs energy, storage adoption, correlation 
heatmaps, outlier detection, and county-level summary.

## **Feature Engineering**
Aggregated 218,115 project rows into 62 county-level rows. 
Applied variance threshold, correlation-based selection, 
silhouette score feature testing, log transformation, and 
StandardScaler. Final 3 features: Total_Energy, 
Total_Projects, Avg_Storage.

## **Clustering**
Implemented and compared three algorithms:
- KMeans — Silhouette: 0.5040, Davies-Bouldin: 0.6882
- DBSCAN — Eliminated after testing 36 parameter combinations. 
  Best silhouette: 0.3335. Excludes counties as noise.
- Hierarchical (Ward, K=3) — Silhouette: 0.5065, 
  Davies-Bouldin: 0.6813. Selected as best model.

## **Fine Tuning**
Tested 12 configurations (4 linkage methods × 3 K values). 
Original ward + K=3 was confirmed as already optimal.

## **Zone Labelling and Map**
Labelled all 62 counties into 3 zones. Built an interactive 
Folium map with popup details per county.

## Results — 3 Production Zones
**Zone 1 — High Production (18 Counties)**
Average 210M kWh per county. Total 3.78B kWh.
Avg 10,897 projects. Avg storage 0.79 kWac.
Counties: Albany, Bronx, Dutchess, Erie, Kings, Monroe, 
Nassau, Orange, Queens, Rensselaer, Richmond, Rockland, 
Saratoga, Schenectady, Suffolk, Tompkins, Ulster, Westchester.
Strategy: Immediate sales priority. Highest ROI.

**Zone 2 — Medium Production (7 Counties)**
Average 104M kWh per county. Total 725M kWh.
Avg 658 projects. Avg storage 14.67 kWac.
Counties: Chenango, Cortland, Fulton, Jefferson, 
Oneida, Onondaga, Oswego.
Strategy: Best solar and storage opportunity. 
18 times more battery storage than Zone 1.

**Zone 3 — Low Production (37 Counties)**
Average 47M kWh per county. Total 1.76B kWh.
Avg 469 projects. Avg storage 0.26 kWac.
Strategy: Long-term growth market. Lowest competition.

## Key Insights

- Suffolk produces 877M kWh — 2.5 times more than Nassau
- 98.1% of projects have zero storage — 214,024 upsell opportunity
- Medium Zone has 18 times more battery storage than High Zone
- Jefferson County leads storage at 46.87 kWac average
- 2023 was the all-time high with 29,452 new projects
- SolarCity is 32% more energy efficient per project than Sunrun

## Interactive Map
View all 62 counties colour-coded by zone with popup details:
https://Keerthana-amin.github.io/Clustering_Solar_Energy_Production_Zones/solar_zones_map.html

## Tools Used
Python, Pandas, NumPy, Scikit-learn, Scipy, 
Matplotlib, Seaborn, Folium, Jupyter Notebook

## Files
- Notebook: 21-step full analysis pipeline
- PDF: 20-slide presentation with 20 charts
- Map: Interactive HTML Folium map
- Excel: Final county cluster assignments

## Author
Keerthana 
