# 2024-11-nj-changes

## Data

This analysis uses 25 spreadsheets.

#### data/demographics:
The .csv files in this folder were retrieved from the United States Census Bureau's website, accessible here:

Using the interactive tables database on the website, filter for the following American Community Survey 5-Year Estimates Data Profiles:
- Selected Social Characteristics
- Selected Economic Characteristics
- Demographic and Housing Estimates

And make sure to filter for the following if recreating the NJ analysis:
- New Jersey, All Counties
- each of the surveys for the following years: 2010, 2012, 2016, 2020, 2022

#### data/employment:

The .xlsx files in this folder were retrieved from the State of New Jersey's Department of Labor and Workforce Development, accessible here: https://www.nj.gov/labor/labormarketinformation/employment-wages/unemployment-rates-labor-force-estimates/

Select the "State, County and Labor Area" tab, then download the following files:
- 2024 County Labor Force Estimates
- County Labor Force Estimates: 2020-2023
- County Labor Force Estimates: 2010-2019
- County Labor Force Estimates: 2000-2009

#### data/party-affiliation:

The pdf files in this folder were retrieved from State of New Jersey's Division of Elections' Statewide Voter Registration Statistics Archive, accessible here: https://www.nj.gov/state/elections/election-information-svrs.shtml

Download General Election Day Voter Registration files for 2024, 2020, 2016, 2012 and 2008. 

## Analysis Preparation

If you just want to run the analysis without all of the cleaning and prep work, then use data/indicators.xlsx.

Each county is in the first column, while the remaining columns include values for a range of indicators to be used for the analysis. 

## Methodology

The notebook notebooks/nj-voter-analysis.ipynb performs the following analyses:

#### Part 1: Basic Information about the dataset

Take a very high-level of the dataset for reference. 

#### Part 2: K-means analysis preparation

The data/indicators.xlsx, for the most part, only includes raw numbers. Data in several columns, therefore, need to be transformed into rates.
Additionally, there are percentages included in the dataset that need to be reversed into rates again. 
We are doing this because K-means analyses work best when all data are on the same scale. In this case, we'll want all data to be on a scale of 0-1. 

#### Part 3: Creating GeoDataFrames

This part of the analysis joins the indicators data with the shapefiles of NJ counties and creates a geodataframe that we can visualize as a map. These maps will be helpful for the next step, so that we can visualize which counties are being grouped together. 

#### Part 4: K-Means Analysis

Finally, a K-means analysis is performed on a select number of indicators for each election year. The analysis results in maps of NJ during each election year, depicting which counties have been grouped together using the k-means analysis. 

## Licensing

All code in this repository is available under the MIT License. The data file in the output/ directory is available under the Creative Commons Attribution 4.0 International (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

## Feedback / Questions?

Contact me at mia.hollie48@journalism.cuny.edu.
