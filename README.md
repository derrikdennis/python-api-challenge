# What's the Weather Like? - Python API Homework <!-- omit in toc -->

For Findings, please click on the findings section of the table of contents

- [Background](#background)
  - [WeatherPy - An analysis of weather data as it related to latitude](#weatherpy---an-analysis-of-weather-data-as-it-related-to-latitude)
  - [VacationPy - Planning future vacations based off of the weather data.](#vacationpy---planning-future-vacations-based-off-of-the-weather-data)
- [Findings](#findings)
  - [WeatherPy Results](#weatherpy-results)
  - [VacationPy Results](#vacationpy-results)
  - [Here are the 9 Cities and the closet hotels:](#here-are-the-9-cities-and-the-closet-hotels)

## Background

### WeatherPy - An analysis of weather data as it related to latitude

In this assignment I was to look at data regarding weather and see if the city location's latitude and longitude had any impact on the weather it faced.

1. More specifically, the first objective's foal was to determine if four different weather phenonemon - temperature, humidity, cloudiness, and wind speed - were directly related to how close they were to the equator.

2. The next objective was to run a linear regression on each of the four different phenonmenon, but to split it out into Northern Hemisphere and Southern Hemisphere data. The results would be:

   - Northern Hemisphere - Temperature (F) vs. Latitude
   - Southern Hemisphere - Temperature (F) vs. Latitude
   - Northern Hemisphere - Humidity (%) vs. Latitude
   - Southern Hemisphere - Humidity (%) vs. Latitude
   - Northern Hemisphere - Cloudiness (%) vs. Latitude
   - Southern Hemisphere - Cloudiness (%) vs. Latitude
   - Northern Hemisphere - Wind Speed (mph) vs. Latitude
   - Southern Hemisphere - Wind Speed (mph) vs. Latitude

3. After each pair of plots, I will explain what the linear regression is modelling such as any relationships and any other analyis I might have.

4. Considerations for this analysis included the following:

- Randomly selecting at least 500 unique cities based on latitiude and longtiude.
- Performing a weather check in each of the cities using a series of sucessive API calls.
- Including a print log of each city as it's being processed with the city name and number
- Saving a CSV of retrieved data and and PNG image of each scatter plot.

### VacationPy - Planning future vacations based off of the weather data.

In the next art of the assignment, I took the weather data from above and used jupyter-gmaps and the Google Places API to identify
cities with "perfect weather".

1.  I created a heat map that displayed the humidity for every city from Pari I of the assignment.

2.  I narrowed down the DataFrame to find my ideal weather conditions. These conditions were:

    - A maximum temperature lower than 80 degrees but higher than 70 degrees.
    - A wind speed less than 10 mph
    - Zero Cloudiness

3.  This brought down the number of cities to a reasonable number.
4.  Take these cities and plot the first hotel within 5000 meters of the city.
5.  This plot would be on top of the hjumidity heatmap with each pin containing:

    - Hotel Name
    - City
    - Country

## Findings

### WeatherPy Results

As we continue to learn about fundamental concepts related to API processesing with Python, we have asked a genearl question, "What does the weather do as you get closer to the equator?"

Here are my three takeaways related to the analyzing of the meteorological data:

- There is a direct correlation between temperature and latitude.
  - In the Northern Hemisphere, for every degree of latitude we add, we take away a degree of temperature (y = -1.0x + 108.22).
  - In the Southern Hemishpere, the slope is a little less (y = -0.73x + 68.12)
- Looking at the linear regression equations for the Northern versus Southern Hemisphers, diverging or flat slopes for both the cloudiness (%) and wind speed indicate that there is no relationship between the two respective variables and latitude.

- In regards to the analysis of humidity versus latitude, while the slopes of the Northern and Southern Hemisphere linear regression equations are somewhat similar (0.13 vs 0.00), I would recommend additional data to be pulled to further the veracity of any claim made.

### VacationPy Results

In the VacationPy file, we determined what cities might be ideal for us to go on vacation (Please suspend your knowledge regarding current conditions related to travel due to the Covid-19 Pandemic)

This analysis selected 9 cities that would be ideal to visit based on a number of meteorological conditions:

- The temperature needed to be between 70 and 80 degrees Fahrenheit.
- It was a perfectly clear day (0% cloudiness)
- The wind speed was less than 10 miles per hour.

We took this list and booked a hotel for you! The hotel that has been selected for you is based of identifying the closest hotel to the city using the Google Maps Places API.

### Here are the 9 Cities and the closet hotels:

|     | City              | Country | Latitude | Longitude | Hotel Name                      | Hotel Address                                                  |
| --: | :---------------- | :------ | -------: | --------: | :------------------------------ | :------------------------------------------------------------- |
| 116 | Noumea            | NC      |   -22.28 |    166.46 | Nouvata                         | 123 Promenade Roger Laroque, Anse Vata, Nouméa                 |
| 346 | São João da Barra | BR      |   -21.64 |    -41.05 | Pousada Kactus                  | R. Q - Chapéu do Sol, São João da Barra                        |
| 469 | Kumluca           | TR      |    36.37 |     30.29 | TurkuazKöy                      | Orta Mah. Barbaros Caddesi No:119 Finke 1, Finike              |
| 472 | Tartous           | SY      |    34.89 |     35.89 | Shahin Tower Hotel              | Tartus‎                                                        |
| 501 | Tripoli           | LY      |    32.88 |     13.19 | Radisson Blu Al Mahary Hotel    | Al Fatah St, The Corniche, Tripoli                             |
| 550 | Mont-Dore         | NC      |   -22.28 |    166.58 | Hotel Restaurant le Vallon Dore | Mont-Dore                                                      |
| 562 | Caborca           | MX      |    30.58 |    -111.1 | Motel Elba                      | Blvrd Guillermo Padrés 201, La Loma, Santa Ana                 |
| 581 | Florianópolis     | BR      |   -27.61 |     -48.5 | Majestic Palace Hotel           | Av. Jorn. Rubéns de Arruda Ramos, 2746 - Centro, Florianópolis |

And yes, Tripoli, Libya is an ideal city to visit!
