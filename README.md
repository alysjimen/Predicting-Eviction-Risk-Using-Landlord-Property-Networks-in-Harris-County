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
3. Census/ACS neighborhood characteristics (not yet applied)

### Identification of Rental Properties

Because HCAD is an appraisal database rather than a rental registry, rental status is not directly observed for every property. The study therefore constructs a reproducible indicator of likely rental housing using multiple HCAD fields. Properties are initially identified as rentals when HCAD provides explicit multifamily or rental-related evidence through building improvement type, property-use classification, or potential gross income category. This includes duplexes, triplexes, fourplexes, garden, mid-rise and high-rise apartments, manufactured-housing parks, subsidized housing, tax-credit housing, and other apartment structures. Properties such as single-family homes, condominiums, and townhouses are not assumed to be rentals solely because they are residential; these properties are subsequently evaluated using additional evidence including homestead exemptions, ownership type, and differences between owner mailing and property addresses.

Rental identification is performed at the HCAD account-year level, while recognizing that a single appraisal account may contain many housing units. The number of HCAD accounts classified as rentals is not expected to equal the Census renter-occupied housing share. As an external validity check, the resulting HCAD rental universe will instead be compared with American Community Survey estimates at the housing-unit level. HCAD unit counts and building characteristics will be used to estimate the number of rental units represented by identified properties, and the resulting totals will be compared with ACS estimates of renter-occupied housing units in Harris County.
This formulation was chosen for simplicity and considers that the numbers are conservative due to a possible exclusion of many single-family rentals, rental condos, and rental townhouses that we will add later.

For 2021, we found 16,297 explicitly rental/multifamily HCAD accounts represent an estimated 637,393 housing units. These properties corresponds to roughly 83% of the approximately 768,000 renter-occupied housing units estimated by the ACS benchmark, providing preliminary support for the coverage of the HCAD-based rental identification procedure. The remaining rental stock is expected to include single-family rentals, rented condominiums and townhouses, and properties that may be incomplete. 

