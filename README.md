# Predicting-Eviction-Risk-Using-Landlord-Property-Networks-in-Harris-County

## Overview

This project investigates whether landlord ownership structure, property characteristics, and neighborhood context can help predict eviction filings in Harris County, Texas to further advice policy and tenants. 

The project combines property appraisal data from the Harris Central
Appraisal District (HCAD) and Harris County JP Court Data. For the study, we will use Graph Neural Network technologies and construct nodes and edges to connect landlords, tenants, and properties and label them based on the eviction JP court data. This project was done under the supervision of Dr. Maryam Tabar at the Data Science for Social Good UTSA lab. 

The methodology was also reference of Preis (2024), *Where the Landlords Are:
A Network Approach to Landlord-Rental Locations*, which models rental
ownership as a bipartite landlord–property network. Instead of offering a representative model of the United States housing market, due to data and law discrepancies by state, we offer to bring about a comprehensive study of the local housing market in Harris County that is most representative of the Texas market. 

The model will be constructed using the Graph Neural Network (GNN)
that predicts whether a residential rental property experiences an eviction
filing based on:

- landlord characteristics (including portfolio structure, percentage of ownership, location as referenced on their tax returns,
- property and building characteristics( location, amenities, type of housing, etc.),
- eviction history and patterns, and
- geographic/neighborhood context(using the ACB).

## Data Sources

1. Harris Central Appraisal District (HCAD) property appraisal data (https://hcad.org/pdata/pdata-property-downloads.html)
2. Harris County Justice of the Peace eviction case records(https://jpwebsite.harriscountytx.gov/PublicExtracts/search.jsp) 
3. Census/ACS neighborhood characteristics (planned)


