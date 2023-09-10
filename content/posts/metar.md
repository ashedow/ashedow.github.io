---
title: "Metar. How to read"
date: 2023-05-29
description: ''
featured_image: ""
tags: ["#aero", "#weather"]
draft: false
---

# How to read METAR

Here’s what a typical METAR looks like:

**METAR KGGG 1617753Z AUTO 14021G26 3/4SM+ TSRA BR BKN008 OVC012CB 18/17 A2970 RMK PRESFR**


![](/images/ReadMETAR.jpg)

So a typical METAR report contains the following information in sequential order:

1. **Type of report**
There are two types of METAR reports. The first is the routine METAR report that is transmitted every hour. The second is a special report, a SPECI, that can be given at any time to update the METAR for rapidly changing weather conditions, aircraft mishaps, or other critical information. So here, it’ll say either METAR or SPECI.

2. **Station id**
K refers to the Continental United States. The three letters after it CLE, refers to the airport. In this case, Cleveland Hopkins Airport.

A four-letter code as established by the International Civil Aviation Organization (ICAO). In the 48 contiguous states, a unique three-letter identifier is preceded by the letter “K.” For example, Gregg County Airport in Longview, Texas, is identified by the letters “KGGG,” K being the country designation and GGG being the airport identifier. In other regions of the world, including Alaska and Hawaii, the first two letters of the four-letter ICAO identifier indicate the region, country, or state. Alaska identifiers always begin with the letters “PA,” and Hawaii identifiers always begin with the letters “PH.” [A list of station identifiers can be found here.](https://aviationweather.gov/metar)

3. **Date and time of report**
Depicted in a six-digit group (161753Z). The first two digits refers to the day of the month.
The next 4 digits 0136 refers to the time when the report was made. The Z refers to ZULU or UTC time.
A “Z” is appended to the end of the time to denote that the time is given in Zulu time (UTC) as opposed to local time. If you ever need to convert UTC/Zulu time to your local time, here’s an online conversion tool: http://www.timeanddate.com/worldclock/timezone/utc

4. **Modifier**
Sometimes the METAR will have a COR or AUTO modifier after the Date & Time.
COR indicates a corrected observation. Disregard the previous transmission. COR 1725 means that the correction was transmitted at 1725Z.
AUTO a refers to an automated observation with measurements taken by equipment such as the domestic Automated Weather Observing System (AWOS) or Automated Surface Observation System
(ASOS), or the Air Force’s Automated Meteorological Station (AMS), also known as AN/FMQ-19. AO1 denotes an observation taken by equipment lacking a precipitation type discriminator (rain vs. snow). AO2 denotes an observation taken by standard equipment with a full complement of sensors. A02A denotes an automated observation augmented by a human observer.

5. **Wind**
Reported with five numbers (14021), unless the speed is greater than 99 knots, in which case the wind is reported with six numbers.( If you see six numbers, you probably don’t want to be operating a UAS.) 

The first three digits 310 is the direction of the wind in degrees in relation to TRUE North. If the wind is variable, then “VRB” will go after the numbers. (Example: *090V180*)
The second numbers 06 mean refer to the wind speed in knots. 
If gusts are present, the next two or three digits following the “G” are the “gust,” the maximum
wind speed in the last ten minutes. 

For example  25015G30KT - wind is blowing from 250 degrees (true) at a sustained speed of 15 knots with 30-knot gusts.

![picture-of-determine-the-runway-directions-wind-direction-degrees-chart](/images/picture-of-determine-the-runway-directions-wind-direction-degrees-chart.jpg)
Wind direction, N=0, E=90, S=180, W=270

5.1 **Wing varying between directions**
A wind variability group will be reported if the wind is variable by 60 degrees or more and the speed is greater than 6 knots. This remark will contain the extremes of the wind directions, separated by “V.” 
For example 
_METAR KBLV 011657Z AUTO 25015G30KT **210V290** 3/8SM R32L/1000FT FG BKN005 01/M01 A2984 RMK A02 SLP034_
Where 210V290 - wind direction varying between 210 and 290.

6. **Visibility**
This refers to the visibility. For example *10SM* = is 10 Statute Miles, *3/4 SM* =  ¾ of a mile.
The largest reportable metric value is *9999*. This value represents a visibility greater than 9000 meters (7 SM or more).

6.1 **Runway Visual Range**
Runway Visual Range (RVR) follows the visibility and begins with the letter “R.” The runway heading will follow the “R,”. The last four digits report the visibility in feet.

For example, *32L/1000FT* = runway visual range for runway 32 Left is 1,000 ft.

At overseas locations, visibility is reported in meters, and FT is omitted from the RVR group. The same RVR at an overseas location would appear as R32L/0300 and read, “runway visual range for 32 Left is 300 meters.” 

M0600FT = “RVR is less than 600 feet.” (M = less than)
P6000FT = “RVR is greater than 6,000feet.” (P = greater than)
R06L2000V4000FT = “RVR for 6 Left is variable between 2,000 and 4,000 feet.” “V” indicates that the RVR is variable between two thresholds. 

6.2 **Present Weather and Obscurations (If any)**
In our METAR report, this isn't included, but let's use `+SHRA`.
The `+` means Heavy, `SH` means Showers and `RA` means Rain. Look at the legend below for the full list of possibilities.

Phenomenon Qualifiers

Intensity:
(-): Light
( ): Moderate [No prefix]
(+): Heavy

Proximity:
VC: In the vicinity
none: On station

Descriptor:
MI: Shallow
BC: Patches
DR: Low Drifting
BL: Blowing
SH: Showers
TS: Thunderstorm
FZ: Freezing
PR: Partial

Types of Weather Phenomenon
Precipitation:
DZ: Drizzle
RA: Rain
SN: Snow
SG: Snow Grains
IC: Ice Crystals
PL: Ice Pellets
GR: Hail
GS: Small Hail &/or Snow Pellets
UP: Unknown Precipitation

Obscuration:
BR: Mist
FG: Fog
FU: Smoke
VA: Volcanic Ash
DU: Widespread Dust
SA: Sand
HZ: Haze
PY: Spray

Other:
PO: Well-Developed Dust/Sand Whirls
SQ: Squalls
FC: Funnel Cloud Tornado Waterspout
SS: Sandstorm
DS: Duststorm

7. **Sky condition**
The next block means the sky conditions. The first three letters *FEW* are the codes for the amount of coverage in the sky.

Sky coverage in eighths:
NCD: No Cloud Detected  (note that laiser ceilometer check directly above the sensor)
SKC: SKy Clear (Manual report)
CLR: CLeaR (Automated report)
FEW: Few -- 0-2 eighths (1/8 to 1/4 of the sky covered)
SCT: Scattered -- 3-4 eighths (3/8 to 1/2 of the sky covered)
BKN: * Broken -- 5-7 eighths (5/8 to 7/8 of the sky covered)
OVC: * Overcast -- 8 eighths (Total sky coverage)

The next three digits *020* mean the amount of feet (in hundreds) in which the clouds are located.

In this first part, we’re seeing the height of the cloud base, which is being reported with a three-digit number in hundreds of feet above-ground-level (AGL). BKN stands for broken clouds, and “008” means 800 feet. So the cloud base is at 800 feet AGL. That’s one thing that’s happening. Then we’re also seeing OVC, which stands for overcast, and the “012” stands for 1,200 ft. So we have overcast clouds at 1,200 ft. AGL. And we’re seeing the type of cloud here too. CB stands for cumulonimbus clouds, and another indicator you might see here is TCU, which stands for towering cumulus clouds.

8. **Temperature and dew point** 
For example - *22/21*
The first two digits 22 represent the temperature in Celsius.
The second two digits 21 represent the dewpoint in Celsius.
To display negative numbers, there will be an **M** in front of the numbers (Example *M04/02* = -04 degress C/ dewpoint: 2).

9. **Altimeter setting**
*A2984* - A Represents "Altimeter". 2984 represents 29.84 inches of mercury for the pressure.

*Q1011* represents a current altimeter setting of 1011 hPa or 1011 mb. 
The 5-character group beginning with Q, following the temperature/dewpoint group is the altimeter setting in hectopascals (hPa), used in some overseas locations. A hectopascal is equivalent to a millibar (mb).


10. **Remarks**
The remarks section always begins with the letters “RMK.” Comments may or may not appear in this section of the METAR. The information contained in this section may include wind data, variable visibility, beginning and ending times of particular phenomenon, pressure information, and various other information deemed necessary. In the above example, PRESFR means “pressure falling rapidly”. Another example of a remark regarding weather phenomenon that does not fit in any other category would be: OCNL LTGICCG. This translates as occasional lightning in the clouds and from cloud to ground. Automated stations also use the remarks section to indicate the equipment needs maintenance.
The remarks section I use to 'decode' the metar remarks is on [dixwx.com](dixwx.com), and use their abbreviations chart for more in-depth information.

