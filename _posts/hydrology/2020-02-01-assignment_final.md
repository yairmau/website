---
toc: true
layout: post
title: Assignment - FINAL
categories: [markdown]
toc: false
tags: [hydrology]
---

## 📒 Instructions
This is where learning happens, not during a lecture. You'll learn a ton of things by doing them yourself. Much success! 😄

Create **two** Jupyter Notebooks called
1. `assignment-FINAL-CODE-IDNUMBER`, and
2. `assignment-FINAL-REPORT-IDNUMBER`,  

where `IDNUMBER` is your 9-digit ID. These are the only files we will check.

## 📌 Locations and data

**Choose one location in the US.**

Download relevant data from NOAA's [Global Summary of the Month](https://gis.ncdc.noaa.gov/maps/ncei/cdo/monthly),  NOAA's [Climate Reference Network Data](https://www.ncdc.noaa.gov/crn/qcdatasets.html), and from the USGS's [National Water Information System](https://maps.waterdata.usgs.gov/mapper/index.html).

Try to find locations with many years of data, the more the better. Take some time to choose your station, plan well. **Choose a location you have not worked with in past assignments.**

## 🛠 Tasks

In this final project, we will integrate the various topics we learned throughout the semester. You will tell a story about the location you chose, and describe the changes it experienced in the past many decades. You can focus on any kind of changes that would influence the hydrological fluxes we learned about. Here are a few examples of changes that you might work on:
* severe droughts in part of the studied period, or an increasing trend in drought severity.
* same as above for rainfall/floods, high temperatures, low temperatures, etc.
* significant changes in land use, such as urbanization, deforestation, agricultural practices, etc.

The list above is not comprehensive, you can choose other factors. Consult with me in case of doubt.

Try to find on the media and in scientific papers evidence for the change you are focusing on. Cite these sources: at least one peer-reviewed scientific paper, and at least 3 other sources, such as a government website, official weather sites, books, reputable news websites, etc.

Can you see the same when analyzing data for the location you chose? Do your findings corroborate the expectation you had when you started this project? If they don't, can you explain why? Did you reach interesting or surprising conclusions in your analysis?

Analyze your location's history with respect to the following:
* Precipitation: seasonality, inter-annual variability, extreme precipitation events and return periods.
* Potential evapotranspiration: Calculate PET using Penman's equation for at least three different years of interest (not necessarily contiguous years). Calculate Thornthwaite's PET for the whole length of the available data (comment about the suitability of Thornthwaite's PET to the location you chose).
* Analyze streamflow statistics in a similar manner as for precipitation: extreme discharge events and return periods.
* Use Budyko's framework to calculate where the location you chose falls on the $(ET/P,PET/P)$ space for at least three different years of interest.

Try to connect the dots: how do your different findings fit together? Discuss what you are trying to show, tell your story with the help of the data and your analyses. If you find things that go contrary to your expectations, can you raise hypotheses of why you see what you see?

You will have one month to hand in your project.  
Much success! 😁

## 🌅 Presentation
All the assignment must be in **one single** Jupyter Notebook. Use markdown cells to discuss the analysis and results, and in code cells show **all the code** you used to produce the figures and data analysis. Leave only the code necessary for your analysis, delete unnecessary lines your wrote while analyzing your data. Don't forget to comment your code, just like we did during exercise sessions.  

The assignment will be written in English.
I am well aware that English is probably not most student's mother tongue, therefore your grade will not be affected by typos nor less-than-perfect English proficiency.  

## 💯 Evaluation

Your assignment will be evaluated according to the following criteria:
* 40% Presentation. How the graphs look, labels, general organization, markdown, clean code.
* 30% Discussion. This is where you explain what you did, what you found out, etc.
* 15% Depth of analysis. You can analyze/explore the data with different levels of complexity, this is where we take that into consideration.
* 10% Replicability: Your code runs flawlessly.
* 5%: Code commenting. Explain in your code what you are doing, this is good for everyone, especially for yourself!


## 🚚 Importing the data

You can use the code from previous assignments and from the exercise lectures.