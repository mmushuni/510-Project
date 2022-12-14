# 510-Project

1. Title: Income Disparity: Comparing Incomes across L.A. Zip Codes.
A 2016 NPR article (article here: https://www.npr.org/sections/thetwo-way/2016/02/25/468120288/a-look-at-the-wealth-and-income-gap-by-zip-code) found vast
differences between economically prosperous and economically poor zip codes, describe a
phenomenon of “Two Americas” occurring side-by-side in the same cities. A Brookings article
dated around the same time (article here: https://www.brookings.edu/opinions/americas-zip-code-inequality/) showed the
same story. With this project, I wanted to examine if this zip code trend could be blown up to
regions of a city. Yes, there is intense income variability from zip code to zip code, even in the
same city, but are lower income zip codes clustered together or are they interspruced with
higher income zip codes? If income inequality is happening at a visibly geographical level, then
perhaps there are geographical constraints or factors that can be examined to point as sources
or causes of the divide.
2. I’ve pushed my requirements.txt in my code folder. In order to reproduce my results, just hit
Cell → Run All in Jupyter Notebooks. Here is the link to my Github Repo:
https://github.com/mmushuni/510-Project.git
3. I collected data from three sources. First off I used the
https://rapidapi.com/trea/api/zippopotam-us API to collect zip codes in L.A. I got around 103 zip
codes from this. Then I used the zip codes with the
https://rapidapi.com/incomebyzipapi/api/income-by-zipcode/ API. I first needed to check that this
API had data for all of the zip codes I used to create my visualization. Some of the zip codes did
not have data, so I collected the ones that did have data in a list. Then I parsed through this list
and collected the median household income for each zip code from that API. Then I organized
each “bucket” of median household incomes to make a more clear visualization. In order to
complete my choropleth map, I needed to collect the coordinate vectors to map the boundaries
of each of the zip codes. For this I used
https://raw.githubusercontent.com/OpenDataDE/State-zip-code-GeoJSON/master/ca_california
_zip_codes_geo.min.json and stored the response, which were the coordinate vectors of every
zip code in california. This is how I mapped using plotly’s choropleth map.
Originally I was using another dataset, which was from the LA Controller’s Office to collect
health care spending. I did not realize until moving along with my project though, that the data
reflected government spending, and not household spending data. So it was not suitable for my
analysis goals. I struggled to find a data source that had health spending separated by zip
codes, so I dropped this part of my analysis.
A challenge I encountered was really just a silly mistake with my data collection. I realized while
finishing my submission for HW 4 that I had typed “la” instead of “los angeles” as the city
parameter for the zip code API. This meant I had gotten the zip codes of every city in California
that started with “la”. So of course, my data did not at all represent Los Angeles. Thankfully, this
was an easy fix.
4. I made a choropleth map using plotly express. I used the github json to get the coordinate
vectors to map the zip code boundaries, specified the zipcodes I wanted mapped, set the
coloration scale to go from light to dark, specified the range of colors I needed, the scope of the
map (the closest I could get was US), set the feature_id to the location of the coordinate vectors
in the json file, and specified how to label the data. Initially, the legend was not very helpful in
understanding the visualization, as it was just boxes with the label and the color. The new
legend is more of a scale, which helps to better understand and interpret the different colors
featured on the map. The figure I made is initially a map of the whole U.S. when it loads, I was
unable to focus the scope at just the state of California initially. From here, you must scroll with
your mouse to zoom in on L.A. Here you can see the various mapped zip codes and their
corresponding coloration. The zip codes with the lowest median household incomes are in the
lightest color and the zip codes with the highest median household income are in the darkest
color. As we can see from the map, lower median household income zip codes are
conglomerated together on the eastern portion of L.A., whereas the (few) higher median
household zip codes are clustered together towards the northwest of LA. From this visualization,
we can understand that zip codes of similar median household incomes are near each other.
We can see a clear indication of income disparity in LA with high income zip codes and low
income zip codes clustered separately from each other. This can have far reaching
consequences such as local funding or availability of resources such as public libraries, public
transportation, public school rating, etc that may be divided differently in these distinctly
separated high and low income zip code areas.
5. Given more time I would like to look into various factors that could be impacted by household
income levels. As the articles from NPR and Brookings state, household income can have
profound effects on educational attainment, future earnings, etc. I would’ve liked to examine
some of these effects from household income. I would’ve done this in a regression, looking
perhaps at household income with respect to single parent status, number of dependents,
educational attainment, etc. I tried to do this initially in the project looking at health care costs to
see if there were differences in health costs across lower and higher income zip codes, but I
struggled to find suitable data.
I would also have been interested to examine the schools that service those zipcodes, and
examine if schools that service lower household income zip codes see differences in test scores
