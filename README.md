# Project: University of Washington, DATA 512 Autumn 2019, Assignment 1
# Title: English Wikipedia page views 2007 - 2019
### Author: Bianca Zlavog
### Goal: Extract monthly aggregated page views for all English Wikipedia pages, process data, and produce a visualization for analysis.
### License: This work is available under an MIT license, included in the repository.
### Assignment instructions: https://wiki.communitydata.science/Human_Centered_Data_Science_(Fall_2019)/Assignments#A1:_Data_curation


## Inputs:

Data was gathered from the Wikimedia REST API, Wikimedia Foundation, 2018. CC-BY-SA 3.0

Wikimedia Foundation REST API terms of use: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions
Legacy Page Count API documentation: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts
Page Views API documentation: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews

Date data was accessed: 10/01/2019


## Data considerations:

* The Page Views API allows filtering to exclude views from web spiders, while the Legacy Page Count API does not.
* The Page Views API separates out mobile traffic into mobile-web and mobile-app access types.
* The parameter names and access type names differ between the Page Views API data and the Legacy Page Count API data. 
	

## Data processing:

1. In the first step, we make the API calls to obtain the raw data in JSON format, and save out raw data files for each query.
2. In the second step, we process and clean the data to prepare it for analysis. We append all the datasets, reshape them wide, clean up column names, and save out a cleaned data file.
3. In the last step, we do a little more data formatting and produce a figure for analysis. We draw some conclusions about the trends in English Wikipedia monthly page views.



## Outputs:

* Seven raw source JSON files as extracted from the API, named in the format: `apiname_accesstype_firstmonth-lastmonth.json`
* One final data file in CSV format named `en-wikipedia_traffic_200712-201809.csv`

	Fields included:

	`year`: year of data in numeric format

	`month`: month of data in numeric format

	`pagecount_all_views`: Total monthly views across all access types from Legacy Page Count API

	`pagecount_desktop_views`: Total monthly views for desktop access from Legacy Page Count API

	`pagecount_mobile_views`: Total monthly views for mobile access from Legacy Page Count API

	`pageview_all_views`: Total monthly views across all access types from Page Views API

	`pageview_desktop_views`: Total monthly views for desktop access from Page Views API

	`pageview_mobile_views`: Total monthly views for mobile access from Page Views API

	Number of observations: 141, spanning from December 2007 to September 2019
	
* One JPEG file named `visualization.jpeg` that depicts the trends in the views data gathered from the API, separated by access type and API source.


------------
## Software used:
------------
* MacOS Mojave 10.14.6
* Python 3.7.1
* ipython 7.2.0

