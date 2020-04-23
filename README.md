# Seattle-Air-BnB
Airbnb, Inc. is an online marketplace for arranging or offering lodging, primarily homestays, or tourism experiences. The company does not own any of the real estate listings, nor does it host events; it acts as a broker, receiving commissions from each booking. The company is based in San Francisco, California, United States.

The company was conceived after its founders put an air mattress in their living room, effectively turning their apartment into a bed and breakfast, in order to offset the high cost of rent in San Francisco; Airbnb is a shortened version of its original name, AirBedandBreakfast.com.

## Focus of Analysis
Using dataset describing the listing activity of homestays in Seattle, WA we will analyse the following three questions:
  - What are the features contributing to Price of the Rental Property?
  - Which localities of Seattle are more expensive?
  - What are the commonly and rarely available amenities? Which amenities are offered in expensive rentals?
  
## Inspiration
Analysis is inspired to learn and have hands on the CRISP-DM Process (Cross Industry Process for Data Mining) and the steps observed to do so are:
  - Business Understanding
  - Data Understanding
  - Prepare Data
  - Data Modeling
  - Evaluate the Results
  
## Files Used
Dataset `listings.csv` available for Seattle Air BnB listings will be used. `SeattleAirBnB.ipynb` is a Jupyter Notebook which contains code as well as is structured to understand the course of analysis. 

## Imports
Libraries numpy, pandas and collections where imported to facilitate Python coding required to analyze the data. Additionally, matplotlib.pyplot was imported to plot graphs, seaborn to create correlation heatmap and gmaps to plot heatmap on google map.

## Analysis
The data is explored to understand which data would meaningfully contribute to the analysis.

For **Finding features Affecting Rental Price**, data related to `host, locality, property, bed/bath, accommodaties, guests, reviews, bookability and cancellation policy` where sliced and cleaned. Bi-categorical data like instant_bookable and host_identity_verified where converted to boolean data while Numercial data like zipcode and price where converted to numerics. All data with missing price, latitude, longitude or zipcode were dropped while neighbourhood data was preserved. 

The rental prices appears to be largely dependent on `number of people it accomodates, how many Beds, Bathrooms or Bedrooms a rental has and if guests are included`. It is higher for `Entire Home/Apt rentals` while it is comapratively lower for `Private Rooms`. High price rentals seems to have `strict Cancellation Policy`.

For figuring out the **expensive localities of Seattle**, we focus on data available for neighborhood and zipcode. It is observed that 10% of Neighbourhood data is missing as opposed to 0.1% of Zipcode data. Additionally, we also use latitude and longitude data to plot map.

While `neighbourhood` data yeilded `Fairmount Park, Industrial District, Portage Bay, Westlake and Alki` as expensive localities while `zipcode` data yeilded `98101, 98119, 98134 and 98199` as expensive localities. Upon plotting Map of our analysis using both neighbourhood and zipcode and comparing it with the map created for all data it can be observed that zipcode analysis was more accurate. It was also observed that neighbourhood `Industrial District` aka zipcode `98134` seems to offer fewer rentals but of higher price range hence making it one of the expensive localities of Seattle.

Based on this analysis the analysis of **features Affecting Rental Price** was **tweaked** to drop neighbourhoods data and to incorporate zipcode data as a categorical data. Initial analysis for features affecting Rental Price was still true. Addditionally price seemed higher for zipcodes 98101, 98109 and 98119 which was coherent with our findings for Pricey Neighbourhood.

Lastly **amenities** was studied. Most of the rentals offered more than one amenity so data was processed to find average price at which each amenity was offered. It was also found how many rentals offers offered any given amenity to analyse its popularity.

In Seattle, `amenities` like `Wheelchair Accessible, Air Conditioning, Pets Allowed and Hot Tub` were offered by `expensive rentals` while amenities like `Elevator, Gym and Intercom` are offered by `economical rentals` as well. Additionally amenities like `Fire extinguisher, Internet and Heating` are `very popular` while amenities like `Breakfast, Pool and Doorman` are `rarely offered`.

## Acknowledgement
The project is formulated by `Udacity` as a part of `Data Scientist Nanodegree Program` and the dataset is part of `Airbnb Inside`. The original source of dataset is available at http://insideairbnb.com/get-the-data.html.

**Wiki**: https://en.wikipedia.org/wiki/Airbnb
