# IBM_DS_certificate_project


**SEGMENTING HAMMERSMITH AND FULHAM WARDS**

                                                                                            6th of June 2021

**REPORT**

---

**I.	INTRODUCTION** 

In this project we will segment ward areas within one parliamentary constituency (Hammersmith and Fulham) in London using Foursquare data on venues in each of the ward.
The results of the analysis will be several clusters of wards which have similar character in terms of the venues and facilities located in the wards and can be used by general public who lives in the constituency or planning to move in the area but not sure which of the wards they will prefer to live in.

---

**II.	DATA DESCRIPTION**

The data on wards was taken from the UK government website - https://www.compare-school-performance.service.gov.uk/download-data
We have limited analysis to the one parliamentary constituency (Hammersmith and Fulham) as this area is quite familiar and it is easier to spot any inconsistencies or limitations in the analysis of the Foursquare data.

Limitations of the Foursquare data:

- foursquare is using coordinates of each ward and radius to load data on venues. Coordinates of each ward is identified through OpenStreetMap. As the result it is almost impossible to catch all venues in the given ward as the shapes of them are different, some streets will be missing due to radius limitations and OpenStreetMap coordinates.

- Foursquare data is not very reliable or objective. The highest number of venues are in the Food categories. Data doesn’t take into account a venue’s size; it can duplicate venues due to radius limitations described earlier in the analysis. Also, the data largely rely on categorization of the users, same type of venues can be classified as cafe or coffee shops. Venue locations are often not in the same area, like places located in Fulham are being ticked as Putney again due to radius.

---

**III.	METHODOLOGY AND EXPLORATORY DATA ANALYSIS**

For this project we have taken government data on schools. The dataset have lots of parameters, so we limited it only to the Hammersmith and Fulham boroughhood and grouped wards of the boroughhood together with number of schools. 

Then using geocoder we have identified geo coordinates of each ward. After checking each on the map and understanding that the data from Foursquare will pick up venues in the given radius we have adjusted geo coordinates for some wards to make the starting point more central.
Then we have downloaded from Foursquare venues for each ward in the radius of 1,000 meters. It is interesting to note that all wards except for one have received 30 venues. After placing venues on the map it was clear that even though we have adjusted wards’ coordinates still Foursquare would load venues outside wards as the shapes of the wards are not round. And as expected some of the busy streets were excluded due to radius. This is a limitation of the analysis using Foursquare, it seems impossible to load accurately all venues within one ward. Hence, the results of this project can be easily distorted and cannot be used on its own.

We have identified TOP 5 most popular venues for each ward and calculated frequencies of each venue for the boroughhood. The highest median and mean belongs to pubs, cafes, coffee shops and parks. 

---

**IV.	RESULTS**

In this project we have analyzed foursquare data on venues and government data on number of schools for wards located in Hammersmith and Fulham council in London.
Using KMeans algorithm we have segmented wards into five clusters.

- Most common venues for cluster 0 are pubs. Unlike cluster 1, other common venues are not only places to eat, but gyms, stadiums, yoga etc.
- Cluster 1 is the most scattered on the map. It has largest number of schools. Most common venues are mainly places to eat.
- Cluster 2 include only one area - Shepher's Bush. Comparing to other clusters it has three venues out of five which are not place to eat, also it does not have pubs / coffee shops / cafes / parks amongst the most common.
- Only one area was allocated to the cluster 3. Cluster three is quite different from others as 5 most common venues include only one place to eat, rest are stores, parks, fields. And looking at the map it can be seen this area is further away from others and has large green area.
- This cluster includes areas with relatively large number of schools. Pubs are the most common venues around the area but quite low frequency of coffee shops and cafes comparing to cluster 0, which is similar to cluster 4. For example, in Ravenscourt park 5 most common venues do not include coffee shops or cafes. And parks are common venues only in one ward, Ravenscourt park.

---

**V.	DISCUSSION**

Foursquare data is not all-encompassing. The highest number of venues are in the Food categories. Data doesn’t take into account a venue’s size; it can duplicate venues due to radius limitations described earlier in the analysis. Also, the data largely rely on categorization of the users, same type of venues can be classified as cafe or coffee shops.

Analysis can be further improved by testing hypothesis if clusters are truly different, if there are statistically significant differences between them.

---

**VI.	CONCLUSION**

Foursquare data is limited but can provide some insights. I suggest it cannot be used alone but maybe as addition to other sources for the purposes of accuracy, completeness, and reliability.
