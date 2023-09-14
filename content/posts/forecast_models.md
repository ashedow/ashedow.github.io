---
title: "Weather forecast models"
date: 2023-09-10
description: ''
featured_image: ""
tags: ["#aero", "#weather"]
draft: false
---

# Weather models

Weather model is a special computer program that solves very complex mathematical equations at specific points on the Earth from a specific set of weather data collected by weather stations, radars, satellites, and other weather instruments for the purpose of making a weather forecast.

## Main types of weather models

[Model comparator](https://weathermodels.com/index.php?r=site%2Fpreview&mode=comparator)
And [some more](https://weathernerds.org/)
And [Model Guidance](https://mag.ncep.noaa.gov/model-guidance-model-area.php)
[Forecasting models charts](https://weather.us/model-charts) and other articles

NWS’s weather and water models:
* http://www.srh.noaa.gov/jetstream/constant/models.html
* http://mag.ncep.noaa.gov/
* http://www.weather.gov/sti/stimodeling_nggps
* http://water.noaa.gov/about/nwm
* http://polar.ncep.noaa.gov/
* ftp://ftp.library.noaa.gov/noaa_documents.lib/NOAA_UMTF/UMTF_overview_2017.pdf


**Global vs Regional models**
Global models produce forecast output for the whole globe, generally extending a week or two into the future. 
Regional models on the other hand have much higher resolutions, but only cover some part (region) of the globe, and only provide forecasts a couple days out in time. 

In addition, all weather models, one way or another, compete for accuracy — or rather, meteorologists who work with them: they share the results and write scientific articles about it... Europeans are believed to be better at predicting weather in temperate latitudes. Americans are slightly better at predicting weather in tropical latitudes because they have hurricanes, but this is debatable.

Why weather models sometimes give inaccurate weather forecasts?

In short, in general, we just can’t measure the weather absolutely accurately.

## Global

### ECMWF (European Centre for medium-range weather forecasts) 

[ECMWF](https://www.ecmwf.int) weather model (European Centre for Medium-Range Weather Forecasts)
Resolution: various (14 km)
* Forecast depth: 10 days
* Step: 3 hours
* Updates frequency: 2 times/day

The ECMWF is a European global forecast seamless model and it is widely regarded as the best and most reliable model currently in existence. It uses a concept called 4D, which is an assimilation that allows the model to be constantly updated as new satellite or other input data becomes available. It is a well-known fact that the ECMWF was the only model that accurately predicted where Hurricane Sandy was moving. 


### GFS (Global Forecast System)

[GFS](https://www.emc.ncep.noaa.gov/emc/pages/numerical_forecast_systems/gfs.php) is a National Centers for Environmental Prediction (NCEP) weather forecast model that generates data for dozens of atmospheric and land-soil variables, including temperatures, winds, precipitation, soil moisture, and atmospheric ozone concentration. The system couples four separate models (atmosphere, ocean model, land/soil model, and sea ice) that work together to accurately depict weather conditions.

* Resolution: 27 km
* Forecast depth: 10 days
* Step: 1 hour
* Updates frequency: 4 times/day

The GFS is the most well-known global weather model and it’s updated every six hours by the American meteorological service. It is actually made up of 4 separate models which work together to paint an accurate picture of weather conditions: atmospheric, ocean, land/soil and sea ice models. However, it doesn’t take topography and shapes of coastlines into account, so it isn’t very accurate for places next to bodies of water. Good for oceans.

The GFS+ is another version of the same model. While the standard GFS27 interpolates data for each point of the 27 km x 27 km square, the GFS+ version always shows the maximum value in each square.

### ICON (ICOsahedral Nonhydrostatic)

[ICON](https://www.dwd.de/EN/research/weatherforecasting/num_modelling/01_num_weather_prediction_modells/icon_description.html)
* Resolution: various (Europe 7km, ICON7), (global 13km, ICON13)
* Forecast depth: 5,1 day
* Step: 1 hour
* Updates frequency: 4 times/day

Created by the German Meteorological Service (Deutscher Wetterdienst), the ICON is generally considered to be even more accurate than the ECMWF due to the better resolution, albeit only in Europe. The most important variables of the ICON are considered to be air density and virtual potential temperature, horizontal and vertical wind speed, humidity, cloud water, cloud ice, rain and snow. Its small-scale part includes the COSMO model, which will be fully integrated into the ICON by 2020. 

At present, the model runs for forecast data distribution are at 00, 06, 12 and 18 UTC. The forecast horizon is +180 hours for the two model runs at 00 and 12 UTC and +120 hours for the other two runs at 06 and 18 UTC. The time interval for the forecast period up to +78 hours is one hour, all other forecast periods beyond +81 hours are covered by a 3-hourly time interval.


ICON, ICON-EU and [ICON-D2](https://www.dwd.de/EN/ourservices/nwp_forecast_data/nwp_forecast_data.html) are very good models and provide excellent results, so we are excited to use ICON-D2 for planning our Alpine adventures.


### UM weather model (Unifef Model)

The UM (Unified Model)[https://www.metoffice.gov.uk/research/approach/modelling-systems/unified-model], also often referred to as the UKMO, is a global model developed in the UK. This model runs every 12 hours, with its output running out to 3 days. Due to its resolution, the UKMET is the most reliable model for the United Kingdom. The global model is considered reliable, and is a base for some regional small-scale models (e.g. New Zealand).

* Resolution: 1.5 km (UK), 10 km (Global)
* Forecast depth: 3 days
* Step: 3 hours
* Updates frequency: 2 times/day


### CFS weather model (Climate Forecast System)

The [CFS](https://www.ncei.noaa.gov/products/weather-climate-models/climate-forecast-system) is a global numerical model. It is produced by the US NOAA NCEP (National Centers for Environmental Prediction). The model is based on 11 years of weather observations. On each calendar date, the straight average value, determined from the available 11 values, is in general composed of the following components: the true climatological annual cycle, meteorological noise, climatological noise, model noise. The model forecast period is 9 months. It may have poor prediction value, but looks useful for long-term planning. 


* Resolution: 108 km
* Forecast depth: 30 days
* Step: 6 hours
* Updates frequency: 4 times/day


## Local

### WRF weather model (Weather Research and Forecasting)

The [WRF](https://www.mmm.ucar.edu/models/wrf) was a result of a collaborative effort of several agencies and laboratories across the globe in the 1980s. It is a codebase for further forecast model processing. It is applicable globally and can take local geography and topography into account. It has a wide range of different physical parameters and demands vast resources to process. Many institutes use the WRF as a base to develop their own regional models.

* Resolution: down to 500 m (8 km in Windy.app)
* Forecast depth: 3 days
* Step: 3 hours
* Updates frequency: once a day

### NAM weather model (North American Mesoscale)

The [NAM](https://www.ncei.noaa.gov/products/weather-climate-models/north-american-mesoscale) is a regional model for North America produced by the American Weather Service. It has a much better resolution than global models such as the GFS and takes small-scale weather phenomena into account, which makes it the most effective model in that region. 


* Resolution: 12 km
* Forecast depth: 61 hours
* Step: 1 hour
* Updates frequency: twice a day


### OS weather model (Open Skiron)

[OS](https://openskiron.org/en/) - a regional high-resolution weather model developed by the University of Athens on the base of the WRF. It is generally regarded as one of the most reliable models for the Mediterranean. 

* Resolution: 12 km
* Forecast depth: 5 days
* Step: 3 hours
* Updates frequency: once a day


### HRRR weather model (High Resolution Rapid Refresh)

[HRRR](https://rapidrefresh.noaa.gov/hrrr/) is local model available for North America
The HRRR is a NOAA real-time 3-km resolution, hourly updated, cloud-resolving, convection-allowing atmospheric model, initialized by 3km grids with 3km radar assimilation. Radar data is assimilated in the HRRR every 15 min over a 1-h period adding further detail to that provided by the hourly data assimilation from the 13km radar-enhanced Rapid Refresh.

* Resolution: 3 km
* Forecast depth: 1.5 days
* Step: 1 hour
* Updates frequency: 24 times/day. update intervals 1 hour (3 hours for Alaska)
* local model for North America

### AROME

AROME is a regional France and the surrounding territories weather model by the Meteo France (French National Meteorological Service). Headquarters: Paris, France.

* Resolution (grid): 1.25 km
* Depth (period): 1,7 days
* Step: 1 h
* Expected update: 5 times a day (every 5 h)

### ALADIN weather model (Aire Limitée Adaptation dynamique Développement InterNational)

The [ALADIN](http://www.umr-cnrm.fr/aladin/) is a consortium sponsored by Météo-France with some countries of Central and Eastern Europe. In 2015, the consortium initiated a partnership with the HIRLAM, with a goal of an integrated management of the two models. Besides the so-called ALADIN model, it has developed the global ARPEGE (55 km grid) and the regional AROME (1.25 km) for France and domains. These two are considered as good ‘chemical’ models, as they take into account chemical additives. The AROME has a very good resolution, thus taking into account many weather parameters, which makes it reliable in Europe. 

* Resolution: various

### GEM weather model (Global Environmental Multiscale Model) 

[GEM](http://collaboration.cmc.ec.gc.ca/science/rpn/gef_html_public/INTRODUCTION/gem_intro.html) 
In North America, this model is often referred to as the CMC (Canadian Meteorological Centre) model. Due to it’s resolution and specialisation, it is the most accurate model for forecasts in Canada.

* Resolution: 2.5 km (Canada), 25 km (Global)

### HIRLAM weather model (High Resolution Limited Area Model)

[HIRLAM](https://www.knmi.nl/home) The regional model covers Northern Europe. This model is a result of cooperation between 10 European meteorological institutes, created with a goal of setting up a numerical short-range weather forecasting system to be operated by all the participating institutes. But originally it is run by the Royal Netherlands Meteorological Institute (KNMI) which is the Dutch national weather service.

* Resolution: 2.5 km

### ACСESS-G weather model (Australian Community Climate and Earth-System Simulator)

[ACCESS](http://www.bom.gov.au/australia/charts/about/about_access.shtml) local weather model provided by Australia's Bureau of Meteorology. Based upon the UK Met Office Unified Model system. ACCESS GS is the global numerical forecast model operated by BoM. It is run four times daily and provides forecast data out to 240 hours with a horizontal resolution of approximately 12 km and 70 vertical levels.

* Resolution: 25 km
* 12 km resolution (ACCESS)
* local model for **Australia**
* update intervals 6 - 7 hours


### RTOFS weather model (Atlantic operational Real Time Ocean Forecasting System)

The [RTOFS](https://luckgrib.com/models/rtofs_global/) is a forecasting model of the Atlantic ocean currents run by the US National Weather Service.

* Resolution: 9 km

### COAMPS weather model (Coupled Ocean Atmosphere Mesoscale Prediction System)

[COAMPS](https://www.cencoos.org/observations/models-forecasts/) This regional weather model covers certain regions bordering the United States and it is run by the American Navy. 

* Resolution: 12 km

### Japan Meteorological Agency 

[JMA](https://www.jma.go.jp/bosai/map.html#5/34.5/137/&elem=root&typhoon=all&contents=typhoon&lang=en)

### Australian Bureau of Meteorology 

[BoM](http://www.bom.gov.au/cyclone/)


### OpenWRF

The Open WRF (Open Weather Research and Forecasting) is a regional Mediterranean weather model by the University of Athens and a group of enthusiasts based on the WRF technology. Headquarters: Athens, Greece.

* Resolution (grid): 4 km
* Depth (period): 2 days
* Step: 1 h
* Expected update: 8 times a day (every 3 h)


### Weather services

[ECMWF](https://www.ecmwf.int/) - is the European Centre for Medium-Range Weather Forecasts.

[wunderground](www.wunderground.com) - Weather Underground has challenged the conventions around how weather information is shared with the public since 1993. by IBM

[wxcharts](https://www.wxcharts.com) by [metdesk](http://www.metdesk.com/)
[Windy](https://www.windy.com/) - gorgeous interactive world map visualizes real-time weather data
[Ventusky](https://www.ventusky.com/) by [inmeteo](https://www.inmeteo.cz/) - Real-Time Weather Conditions on a Beautiful, Interactive Live Map
[Meteo pl](https://maps.meteo.pl/) - UM and COAMPS 
[Finnish Meteorological Institute (FMI)](Ilmailusaa.fi) - ECMWF with local HIRLAM model. Maintained by FMI is the official distribution channel for the aviation weather services in Finland along with AFS. Since the beginning of 2020 the website serves also as a self-briefing system including all weather charts and messages globally required by ICAO and EU regulation.
[meteo](http://meteo.rlp.cz/) - Air navigation service of the Czech Republic
[buienradar](https://www.buienradar.nl)

### Sensors and sources

Meteo stations maps

[databasin](https://databasin.org/datasets/15a31dec689b4c958ee491ff30fcce75)

[noaa](https://www.ncdc.noaa.gov/cdo-web/datatools/findstation)

[purpleair](https://www2.purpleair.com/)

[SaveEcoBot](https://www.saveecobot.com/) is an environmental map and chatbot with an independent air quality sensors network run by non-profit organisation SaveDnipro with an aim to defend environmental rights of the people in developing countries.

[Exposure and Dose Rates](https://www.epa.gov/radnet/about-exposure-and-dose-rates) - US Radiation

The EUropean Radiological Data Exchange Platform (EURDEP) - Europe Radiation. [WHO](https://www.who.int/news-room/questions-and-answers/item/radiation-ionizing-radiation)


[EUMETSAT](https://www.eumetsat.int/) - European Organisation for the Exploitation of Meteorological Satellites.

[DWD](https://www.dwd.de/) The Deutscher Wetterdienst is a public institution with partial legal capacity under the Federal Ministry for Digital and Transport.

[Open Data Weather](https://www.dwd.de/DE/leistungen/opendata/hilfe.html;jsessionid=D8FF12A48DF4FA8FB55288CA16420FF9.live31081?nn=495490) - Erläuternde Dateien (content in general)

[OpenAQ](https://openaq.org/#/community/projects) is a non-profit organisation that has built the world’s largest open-source air quality data platform aggregating and harmonizing air quality data from reference-grade and low-cost sensor sources. By connecting communities with open data, OpenAQ aims to support the work of scientists, journalists, educators, entrepreneurs, community activists, and other air quality advocates fighting air inequality across the globe.

[WMO](https://public.wmo.int/en) - World Meteorological Organization (WMO)

AVIATION WEATHER CENTER [AWC](https://www.aviationweather.gov/)

storm track forecast are:
National Oceanic and Atmospheric Administration
*[NOAA AT](https://www.nhc.noaa.gov/?atlc)
*[NOAA EP](https://www.nhc.noaa.gov/?epac)
*[NOAA CP](https://www.nhc.noaa.gov/?cpac)


**Local models - America:**
* [NAM-3km (NAM CONUS)](https://weather.us/model-charts/conus-hd/usa/temperature-f/20210708-2100z.html)
* [HRRR](https://weather.us/model-charts/rapid-us/usa/temperature-f/20210708-2100z.html)

## ICAO
The [ICAO](http://www.icao.int/) specifies the following standard products for flight planning purposes:
* WAFS products
* METAR
* TREND (forecast of meteorological conditions at the destination aerodrome)
* TAF
* SIGMET
* Take-off forecast (meteorological conditions upon departure)
* Volcanic ash advisories
* GAMET (forecasts of significant meteorological conditions at low levels)/AIRMET for low level flights
* Airport weather warnings
* Information from meteorological satellites
* Information from ground-based weather radar systems
* Space weather advisories.
* The following information concerning the prevailing and predicted meteorological conditions along the entire fligt route, at the airport of intended landing, and at any alternate destination aerodrome must also be made available:

Upper wind and upper-air temperature
Upper-air humidity
Geopotential altitude of flight levels
Flight level and temperature of the tropopause
Direction, speed and flight level of maximum wind
CB clouds
Icing
Turbulence
Turbulence in clouds
Significant weather phenomena.


Good collection of topics about weather condition https://windy.app/blog/big-collection-of-articles-about-weather-forecasting.html

ICAO standarts https://www.icao.int/airnavigation/METP/Pages/default_old.aspx

Weather Conditions Worldwide https://www.icao.int/safety/iStars/Pages/Weather-Conditions.aspx

https://windy.app/blog/what-is-a-weather-forecast-model-guide-on-forecast-models-all-around-the-world.html

https://windy.app/blog/the-collection-of-articles-about-weather-models.html

https://windy.app/support/windy-app-weather-forecast-models.html

https://windy.app/news/icon-d2-weather-model-central-europe.html