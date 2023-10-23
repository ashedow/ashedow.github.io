---
title: "Geodata notes"
date: 2023-10-15
description: ''
featured_image: 
tags: ["#geo", " #data", "#note"]
draft: false
---

# Glossary of geodata

* Attributes: the meanings or labels of a data point
* Coordinate (reference) system (CRS): metadata describing the space in which coordinates exist, e.g. origin, axes, units, etc.
* Coordinates: numbers describing a data point's position within a CRS.
* Datum: a precise reference frame calculated from a collection of known reference points; one part of a GCS.
* Ellipsoid: a mathematical approximation of the size and shape of the earth; one part of a GCS.
* Extent: the minimum and maximum values of the 
* Geographic coordinate system (GCS): a coordinate system with angular longitude,latitude units in degrees; composed of a datum and an ellipsoid.
* Geoid: an imaginary surface similar to sea level if landmasses were "cut away"; unlike the smooth ellipsoid, the geoid is lumpy due to regional variations in gravity.
* GNSS: global navigation satellite system for precisely global positioning; the most common are GPS , GLONASS , BeiDou , and Galileo .
* Project: the act of converting coordinates from a ellipsoidal longitude,latitude GCS to a planar x,y PCS using a projection.
* Projected coordinate system (PCS): a planar coordinate system with Euclidean x,y units (not angles); composed of a GCS and a projection.
* Projection: an algorithm for converting angular longitude,latitude coordinates in a GCS to a plane (a PCS) on/near the Earth's surface, e.g. Mercator, Equidistant Conic, Stereographic, Dymaxion. Different zones (e.g. UTM) are the same fundamental projection with different parameters.
* Redefine projection: the act of changing the coordinate system without changing the coordinates.
* Reproject: the act of changing the coordinate system and changing the coordinates. Typically done by unprojecting from the PCS to the old GCS, transforming to new GCS (if different), and projecting to the new PCS.
* Transform: the act of changing between two GCSs. There are often multiple transformation algorithms for a given pair of GCSs; the best choice depends on the location of your data within the GCS.
* Unproject: the act of converting coordinates from a planar x,y PCS to an ellipsoidal longitude,latitude GCS; the inverse of project.

## links

[Coordinate system transformation of value pairs on-line (cs2cs)](https://mygeodata.cloud/cs2cs/)

[Debunking map myth #1: All coordinates are in “Latitude/Longitude”](http://www.atlefren.net/post/2014/09/debunking-map-myth-1-all-coordinates-are-in-latitudelongitude/)

[Debunking Map Myth #4: The earth is round](http://www.atlefren.net/post/2014/10/debunking-map-myth-4-the-earth-is-round/)

[Debunking map myth #8: Scale numbers works on a screen](http://www.atlefren.net/post/2014/09/debunking-map-myth-8-scale-numbers-works-on-a-screen/)

[Falsehoods programmers believe about maps](http://www.atlefren.net/post/2014/09/falsehoods-programmers-believe-about-maps/)