# python-api-challenge### Data Extraction and Analysis of *Weather Patterns of 500+ Cities* using Open Weather API and JSON traversals ### Identification/Visualization of *Ideal Vacation Spots* using  Google Places API and Jupyter-gmaps library.## Table of contents* [Introduction ](#introduction )* [Objectives ](#objectives)* [Observations and Insights ](#observations-and-insights)* [Technologies](#technologies)* [Code](#code)* [Status](#status)* [Acknowledgement ](#acknowledgement )* [Contact](#contact)## Introduction__Part I - WeatherPy__  : *Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, we will be utilizing a simple Python library, the OpenWeatherMap API, and a little common sense to create a representative model of weather across world cities.*### Objectives#### Data Extraction and Wrangling: - Randomly select at least 500 unique (non-repeat) cities based on latitude and longitude. - Perform a weather check on each of the cities using a series of successive API calls. - Include a print log of each city as it's being processed with the city number and city name. - Save a CSV of all retrieved data and a PNG image for each scatter plot.#### Data Analysis and Visualization:- Create a series of scatter plots to showcase the following relationships:	* Temperature (F) vs. Latitude	* Humidity (%) vs. Latitude	* Cloudiness (%) vs. Latitude	*  Wind Speed (mph) vs. Latitude-  Run linear regression on each relationship. separating the plots into Northern Hemisphere    (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):	* Northern Hemisphere - Temperature (F) vs. Latitude	* Southern Hemisphere - Temperature (F) vs. Latitude	* Northern Hemisphere - Humidity (%) vs. Latitude	* Southern Hemisphere - Humidity (%) vs. Latitude	* Northern Hemisphere - Cloudiness (%) vs. Latitude	* Southern Hemisphere - Cloudiness (%) vs. Latitude	* Northern Hemisphere - Wind Speed (mph) vs. Latitude	* Southern Hemisphere - Wind Speed (mph) vs. Latitude- Explain what the linear regression is modeling. Describe any relationships you notice and any other    analysis you may have.__Part II - VacationPy__  : *Python script to plan future vacations using jupyter-gmaps and the Google Places API with the weather data that was extracted previously.*### Objectives#### Data Munging/Analysis and Visualization : - Create a heat map that displays the humidity for every city from Part I. - Narrow down the DataFrame to find your ideal weather condition.	* A max temperature lower than 80 degrees but higher than 70.	* Wind speed less than 10 mph.	* Zero cloudiness.#### Data Extraction/Analysis and Visualization:- Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.- Plot the hotels on top of the humidity heatmap with each pin containing the Hotel Name, City, and Country.## Observations and Insights ### Overall Summary: - __City Temperature vs. Latitude:__	- Max Temperature of cities peak at the Equator (lat =0) and gradually drops with latitude moving 	  towards 90 and -90 degrees.![Temperature vs. Latitude](./Images/cityLat_Vs_MaxTemp.png)    - __Northern Hemisphere - Temperature (F) vs. Latitude:__	-  R value -0.73 shows that temperature in Northern Hemisphere has strong positive correlation 	   with Latitude  Ie, 73% of variation in data has been accounted for by linear regression equation. 	- This shows why Cities falling under the Latitude 10 to 30 experience pleasant temperature while              cities falling above Lat 35 have cold weather.![Temp North vs. Latitude](./Images/NorthHemp_CityLat_vs_MaxTemp.png) - __Southern Hemisphere - Temperature (F) vs. Latitude:__	- R value -0.47 shows that temperature in Southern Hemisphere has moderate positive correlation             with Latitude ie, 47% of variation in data has been accounted for by linear regression equation. 	- This shows why temperature increases with decrease in latitude from 90 to 0 in Northern  	  	  Hemisphere and decreases with decrease in latitude in Southern Hemisphere.	- Cities in Southern Hemisphere Close to the Equator (lat 0 to -30) might experience pleasant              temperature, while cities away from the 'Equator' (Lat <-30) experience lower Temperature.![Temp South vs. Latitude](./Images/southHem_LatVsTemp_LR.png) - __Humidity vs. Latitude:__- __Northern Hemisphere -Humidity vs. Latitude::__	- R value 0.13 shows that there is a weak correlation between Humidity and Latitude on the 	   Northern Hemisphere   accounting for only 13% of the data. 	- This should be why Northern Hemisphere (Latitude 40-60) seem to experience greater Humidity	  in the plot.![North Humidity vs. Latitude:](./Images/NorthHem_LatVsHumidity_LR.png) - __Southern Hemisphere -Humidity vs. Latitude::__	- R value 0.02 shows that there is a very weak correlation between Humidity and Latitude on the 	   Southern Hemisphere  accounting for only 2% of the data. 	-  There is a weak increase in humidity towards the Equator which is explained by Linear regression              equation.	-  Most Cities have Humidity over 60% which could be related to other factors independent of               Latitude.![South Humidity vs. Latitude:](./Images/southHem_LatVsHumidity_LR.png) - __Cloudiness vs. Latitude:__- __Northern Hemisphere -Cloudiness vs. Latitude:__	- R value 0.02 shows that there is a very weak correlation between Cloudiness and Latitude which 	  is explained  by LR equation accounting for only 2% variance in the data.	- Which explains why cities falling in latitude 35 to 75 degrees have more cloudiness.![North Cloudiness vs. Latitude:](./Images/NorthHem_LatVsCloudiness_LR.png)  - __Southern Hemisphere -Cloudiness vs. Latitude:__	- R value 0.06 shows that there is a very weak correlation between Cloudiness and Latitude 	   accounting for only 6% of the data.	- Which explains why cities close to the equator (lat =0)  have more cloudiness.![South Cloudiness vs. Latitude:](./Images/southHem_LatVsCloudiness_LR.png) - __Wind Speed vs. Latitude:__- __Northern Hemisphere -Wind Speed vs. Latitude:__	- R value 0.0171 Shows that there is a no correlation between windspeed and Latitude 	- Most cities in Northern Hemisphere have wind speed 0 to 20 mph while in Southern Hemisphere 	   have very low wind speed of 0-20 mph.![North Wind Speed vs. Latitude:](./Images/NorthHem_LatVsWindSpeed_LR.png)    - __Southern Hemisphere -Wind Speed vs. Latitude:__	- R value 0.01 shows that there is no correlation between latitude and windspeed.	- Most cities in Southern Hemisphere have very low wind speed of 0-10 mph.![South Wind Speed vs. Latitude:](./Images/SouthHem_LatVsWindSpeed_LR.png)  - __VacationPy Humidity Heat Map:__![Heat Map:](./Images/heatmap.png)  - __VacationPy IIdeal vacation Spots:__	- Pins containing the Hotel Name, City, and Country.![Ideal vacation Spot:](./Images/Ideal_hotels.png) ## Technologies* git Bash* Jupyter notebook### Python Modules and libraries* pandas * citipy* scipy* matplotlib.pyplot* numpy* requests* time* gmaps### APIs* [OpenWeatherMap API](https://openweathermap.org/api)* Google Places API## Code - [WeatherPy Script](/WeatherPy/WeatherPy.ipynb)- [VacationPy Script](/VacationPy/VacationPy.ipynb)## StatusProject Complete## ContactCreated by [Divyashettyk@gmail.com](#divyashettyk@gmail.com)