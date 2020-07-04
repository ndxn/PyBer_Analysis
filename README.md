# PyBer Analysis Report

## Background and Results

This report is being prepared response to the request by V. Isualize which built off the previous data analysis and representation in order to provide a wide angle view of Pyber's operations across different markets. The analysis for the requested technical deliverables, a summary DataFrame and a multiple-line graph, was built off of the lead-up analysis in that it involved accessing informatoin via ```groupby()``` from the merged DataFrame that came from the original CSV files. The results of the technical analysis follow.

### Technical Analysis
Various groupby() operations on the original dataset provided the Total Rides, Total Drivers, and Total Fares, off of which averages were calculated. See the data frame in Table 1.
**Table 1.** Summart DataFrame displaying drive counts, total fares, and averages 
|          |   Total Rides |   Total Drivers | Total Fares   | Average Fare per Ride   | Average Fare per Driver   |
|:---------|--------------:|----------------:|:--------------|:------------------------|:--------------------------|
| Rural    |           125 |              78 | $4327.93      | $34.62                  | $55.49                    |
| Suburban |           625 |             490 | $19356.33     | $30.97                  | $39.50                    |
| Urban    |          1625 |            2405 | $39854.38     | $24.53                  | $16.57                    |
It is worthy noting some inversely related trends between the city types. Namely, on the urban end of the spectrum, Pyber is taking in more fares but over many more rides, whereas on the rural end of the spectrum, the average fare per ride is much higher. The same trend goes for average fare per driver. On the urban end of the spectrum, the issue is so pronounced that there are actually more drivers than rides given, meaning that some drivers will receive no fares.

The second technical analysis deliverable, Figure 1., represents the total fares brought in weekly for the first four months of 2019. 

![Image]/(analysis/Fig8.png)

The practical value of the multiple-line graph is showing the distinct difference in the amount of fares brought in over the different types of cities. As expected, urban cities account for the largest amount of fares while rural cities account for the least amount of fares.

## Challenges Encountered and Overcome

For a majority of this project, the coding and results came smoothly. The summary DataFrame came together quite nicely using the available data and ```groupby()```. What followed with the analysis leading up to the creation of the line chart, however, was a different story. The use of pivot was completely foreign and I was taken aback by the number of times it became necessary to reset the index and to create new DataFrames. With the amount of manipulation of DataFrames, I did come to appreciate that creating new DataFrames can reduce the chance of downstream issues.

Speaking of downstream issues, I came across one problem that vexxed me for quite some time. As ```resample()``` was new to me, I spent a lot of time trying figure out if the error was with my use of the operation or with the data going in. With enough debugging, I centered on the issue being, primarily, that of the datatype of the index. With that identified, I was able to overcome the issues I had by looking for a practical, not difficult solution and apply it at the right step in the code. It was a frustrating, not at all fulfilling excercise but I am glad I fixed the issue myself (with the help of learning assistants and TA office hours).

### Recommendations for Future Analysis

As with any data analysis, there's always more that can be done and the only limits are the depth of a company's coffers. From the existing analysis, my recommendations to V. Isualize would be to recruit more drivers in rural and suburban areas in order to expand the market there. The best way to address urban markets would be to expand ridership through marketing.

### Additional Analysis 1

Additional analysis that should be undertaken as more data comes in would be that of a regression in order to predict future trends. A basic way to begin this would be a rigorous analysis of the central tendencies and using other known variables to fit in a multivariate regression. The results from the regression would look stellar on a scatter plot.

### Additional Analysis 2

A second recommend analysis--and one that can be undertaken with the existing data--is to take a more granular approach reading out trends in the cities. Daily and, when more rides are available, hourly fares will be important to know as cities of all sizes have predictable traffic patterns that can be capitalized on.

This analysis would use a similar ```resample()``` operation but with much smaller time bins. Instead of totalling fares, as they represent whole rides which may or may not be encapsulated in just one time bin, ride counts might be more appropriate as they can be counted from the time of origin, which will be most helpful in sorting out and planning for trends.