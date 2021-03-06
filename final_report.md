Final Report
================
12/6/2021

### Motivation

One of our group members’ had the unfortunate experience of getting her
car towed last year, due to parking near by a fire hydrant in Minnesota.
A news report published by New York Post about locations drivers were
most likely to get a parking ticket in NYC between October 2020 and
September 2021
[-Link](https://nypost.com/2021/11/18/these-are-the-worst-nyc-streets-for-getting-a-parking-ticket/).
We were intrigued by the potential of investigating the parking
violation in NYC in 2021.

### Questions

1.  When and where a parking ticket in NYC is most likely to be found?
2.  what possible factors are associated with the tickets? The driver’s
    experience, the car’s size?
3.  how to avoid the future ticket? Suggestions based on the analysis…

### Data

#### Data Processing and Cleaning

We used two datasets from NYC OpenData in our project:

-   Open Parking and Camera Violations
    [-Link](https://data.cityofnewyork.us/City-Government/Open-Parking-and-Camera-Violations/nc67-uf89)

The Open Parking and Camera Violations contains violations from 2016 to
2021 and have 73.6 millions of rows. Since we only focus on year 2021
from January to October, we filter the dataset on the website page to
remove redundant information and download the dataset after filtering.
The dataset we used was too large to store in github. We are interested
in parking violation in five boroughs, Manhattan, Kings, The Bronx,
State Island, and Queens. The original variable `county` renamed as
`borough` and names are aligned. We separated the `issue_date` into
`month`, `date`, and `year` and apply function to find the weekday of
the date. We further broke down the `violation_time` into `hour` and
`min` for plotting the violation over a day.

-   Parking Violations Issued - Fiscal Year 2021
    [-Link](https://data.cityofnewyork.us/City-Government/Parking-Violations-Issued-Fiscal-Year-2021/kvfd-bves)

The Parking Violations Issued - Fiscal Year 2021 dataset provides
information about the violations issued during the respective fiscal
year. We extract the information about the location where parking
violation issused in 2021. The variables we count on are `House Number`,
`Street Name`, `Intersecting Street`. We would combine the contents from
those columns and draw the complete address where violation happened.
These addresses would occur as a data point in the map for data
visualization.

After data cleaning, the two datasets are joined by `summons_number`
finally.

#### Variable of Interests

**Open Parking and Camera Violations**

-   `plate`

-   `issue_date`

-   `violation_time`

-   `violation` : type of violation

-   `fine_amount`

-   `borough`

-   `weekday`

**The Parking Violations Issued - Fiscal Year 2021**

The key variables that we used in our analysis include for mapping

-   `House Number`

-   `Street Name`

-   `Intersecting Street`

### Exploratory Analysis

**Open Parking and Camera Violations**

We use the dataset to explored about the distribution of number of of
violation and violation types in five boroughs to understand the trend
of violation in NYC. Then, we explored the distribution of number of
violation over a day and in each weekday.

#### 

#### Visualization over time

We export the complete parking violation address from the Parking
Violations Issued - Fiscal Year 2021 dataset. The package of
tidygeocoder makes getting data from geocoding services easy. We import
the address data and get the return of latitudes and longitudes via
Google Api. Dropping the null value, we obtain the csv file containing
latitudes and longitudes of parking violation address. Then we adopt the
file to visualize geographical data on the map in
[kepler](https://kepler.gl/). The shining points reveal the parking
violation sites distribution.

### Additional Analysis(Regression Analysis)

### Discussion

### Conclusion
