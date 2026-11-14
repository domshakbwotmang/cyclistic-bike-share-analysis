# Cyclistic Bike-Share Analysis

## Google Data Analytics Capstone Project

**Author:** Domshak Bwotmang  
**Analysis period:** October 2025 – September 2026  
**Tools:** Python, Pandas, Matplotlib, PyArrow, SQLite, JupyterLab  
**Data source:** Divvy Bike-Share Historical Trip Data

---

## 1. Project Overview

This project examines differences in bike-share usage between casual riders and annual members.

The analysis follows the fictional Cyclistic business scenario from the Google Data Analytics Professional Certificate. Real-world historical Divvy bike-share trip data from Chicago is used as the analytical dataset.

The central business question is:

**How do casual riders and annual members use the bike-share service differently, and what evidence-based opportunities could help convert casual riders into annual members?**

The project applies data preparation, quality control, exploratory analysis, visualisation and business-oriented interpretation to address this question.

## 2. Business Objectives

The analysis aims to:

- Compare trip activity between casual riders and annual members.
- Examine differences in ride duration.
- Identify weekly and monthly usage patterns.
- Compare bike-type distributions.
- Investigate selected weekday-morning station-return patterns.
- Develop evidence-based recommendations for membership marketing and further investigation.

## 3. Dataset

The project uses 12 monthly Divvy historical trip-data archives covering October 2025 through September 2026.

The original dataset contains 13 columns describing trip identifiers, rider categories, bike types, timestamps and station information.

After reporting-period filtering and duplicate removal, the cleaned master dataset contains **6,171,679 records**.

A separate duration-eligible dataset contains **6,146,323 records** and is used for duration-based analysis.

Original source archives and processed datasets are not included in this public repository. Users must obtain the source data from the official provider and review the applicable data licence.

## 4. Data Preparation and Quality Control

The preparation process included:

- Combining the 12 monthly source archives.
- Standardising and validating relevant fields.
- Restricting records to the defined reporting period.
- Identifying and removing confirmed duplicate records.
- Engineering six analytical variables.
- Evaluating duration-quality issues.
- Separating the full cleaned dataset from the duration-eligible dataset.
- Validating the resulting datasets before analysis.

Duration exclusions were applied only to duration-based analysis. They were not removed from the full master dataset.

## 5. Key Findings

The analysis produced several findings:

1. Annual members accounted for approximately 64.53% of recorded trips, while casual riders accounted for 35.47%.
2. Casual trips had a higher mean and median duration than member trips.
3. Casual trip activity was higher on weekends, while member trip activity was higher on weekdays.
4. The casual share of monthly trips increased from January 2026 through July 2026.
5. Electric-bike trips represented a larger share of casual trips than member trips.
6. Casual riders recorded longer mean durations than members across both classic and electric bikes.
7. A secondary weekday-morning analysis identified differences in short-duration, same-station trips between rider categories.

These findings describe recorded trip patterns. They do not independently establish rider motivations, trip purposes or the causes of observed differences.

## 6. Business Recommendations

The findings inform five proposed areas for further testing:

- Weekend membership-acquisition campaigns.
- Seasonal membership-acquisition campaigns.
- Duration-based membership messaging.
- Electric-bike usage in campaign segmentation and testing.
- Further investigation of short-duration, same-station trips.

These are evidence-informed proposals, not proven conversion strategies. Controlled experiments and additional customer and campaign data would be required to evaluate their effectiveness.

## 7. Repository Structure

```text
cyclistic-bike-share-analysis/
│
├── data/
│   └── reference/
│       └── stage71_data_provenance.csv
│
├── notebooks/
│   ├── 01_data_inventory_rebuild.ipynb
│   └── 02_data_rebuild.ipynb
│
├── visualizations/
│   ├── 01_rider_composition.png
│   ├── 02_ride_duration_comparison.png
│   ├── 03_weekly_activity_patterns.png
│   ├── 04_monthly_rider_seasonality.png
│   ├── 05_bike_type_distribution.png
│   └── 06_duration_by_bike_type.png
│
├── .gitignore
├── environment.yml
└── README.md
```

Raw archives, processed datasets, temporary databases and notebook checkpoints are excluded from version control.

## 8. Reproducing the Analysis

### Requirements

- Git
- Miniforge, Miniconda or Anaconda
- Access to the original Divvy historical trip data

### Step 1: Clone the repository

```bash
git clone https://github.com/jdomshak/cyclistic-bike-share-analysis.git
cd cyclistic-bike-share-analysis
```

### Step 2: Create the Conda environment

```bash
conda env create -f environment.yml
```

### Step 3: Activate the environment

```bash
conda activate cyclistic
```

### Step 4: Obtain the source data

Download the 12 monthly historical archives covering October 2025 through September 2026 from the official Divvy data portal.

Place the original ZIP archives in:

```text
data/raw/
```

The original archive filenames and expected data structure should be preserved.

### Step 5: Run the notebooks

Start JupyterLab:

```bash
jupyter lab
```

Run the notebooks in the documented order:

1. `01_data_inventory_rebuild.ipynb`
2. `02_data_rebuild.ipynb`

The notebooks document the data preparation, quality-control and analytical workflow.

**Note:** Reproduction may require updating file paths or adapting notebook cells if the source data structure or software versions change.

## 9. Visualisations

The repository includes six visualisations covering:

- Rider composition.
- Ride-duration comparison.
- Weekly activity patterns.
- Monthly rider seasonality.
- Bike-type distribution.
- Duration by bike type.

Each visualisation supports the corresponding analytical findings documented in the project.

## 10. Limitations

Important analytical limitations include:

- The study covers one 12-month reporting period.
- Trip records do not represent unique individual customers.
- Trip purpose and rider motivations are not directly available.
- Some station information is incomplete.
- Duration-based findings use a separately defined eligible dataset.
- Observational patterns do not establish causation.
- Findings from Divvy data should not automatically be generalised to Cyclistic or other bike-share systems.

## 11. Data Sources and References

1. Divvy System Data: https://divvybikes-marketing.lyft.net/system-data
2. Divvy Data License Agreement: https://divvybikes.com/data-license-agreement
3. City of Chicago Divvy Trips Dataset: https://data.cityofchicago.org/Transportation/Divvy-Trips/fg6s-gzvg/about_data
4. Google Data Analytics Professional Certificate: https://www.coursera.org/professional-certificates/google-data-analytics

Users should review the applicable source-data licence before downloading, reusing or redistributing the data.

## 12. Project Disclaimer

This is an independent educational case study based on the fictional Cyclistic business scenario and real-world Divvy historical trip data.

It is not an official analysis commissioned, approved or endorsed by Cyclistic, Divvy, Lyft or the City of Chicago.

---

**Author:** Domshak Bwotmang  
**GitHub:** https://github.com/jdomshak/cyclistic-bike-share-analysis