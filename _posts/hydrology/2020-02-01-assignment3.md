---
toc: true
layout: post
title: Assignment 3
categories: [markdown]
toc: false
tags: [hydrology]
---

## 📒 Instructions
This is where learning happens, not during a lecture. You'll learn a ton of things by doing them yourself. Much success! 😄

Create a Jupyter Notebook called `assignment-03-IDNUMBER`, where `IDNUMBER` is your 9-digit ID. This is the file only file we will check.

## 📌 Locations and data

**Choose one location in the US.**

1. Import streamflow data from USGS's [National Water Information System](https://maps.waterdata.usgs.gov/mapper/index.html). Choose on the map any measuring station you see fit. Make sure there is available discharge data (usually given in cubic feet per second) in small time intervals, e.g., every 15 minutes.
 * Some of the sites provide precipitation data as well, then point 2 below is unnecessary.
 * On the map you can show "Atmospheric Sites" as well. You can download precipitation data from there.

2. Go to NOAA's [Climate Reference Network Data](https://www.ncdc.noaa.gov/crn/qcdatasets.html) website. The sub-hourly (5-min) data contains information on many variables, we are interested in precipitation.

**Attention!** Some os the USGS stations provide precipitation data. If you find one such station, step 2 above is unnecessary. If you only find discharge data in the USGS website, then make sure you choose two stations in very close proximity (USGS and NOAA). Because there are only a few high-resolution NOAA stations, you might want to start from there and then find discharge data for a stream near the NOAA station.

Bottom line: you are looking for precipitation and stream discharge data, for stations in close proximity, with a high temporal resolution (5 min, 15 min, etc).

## 🛠 Tasks

Choose a rain event of a few hours in your data set. Find the rate of effective water input (p*) and the event flow rate (q*). Analyze the data in a similar was as done during class (various graphs explaining what you see). Find also the characteristic times of the event (centroid lag $T_{LC}$, and centroid lag-to-peak $T_{LPC}$).

Try to find information on the climate, geography, soil, and land use of the watershed. Begin the assignment by explaining about the watershed you chose and characterizing it. When presenting the data and your analyses, discuss what you see based on the concepts learned in class (infiltration, runoff generation, and the factors that affect them). Does the information you found match what you see? What makes sense, and what doesn't?

Discussion is important!

You will have **two weeks** to deliver your assignment. You should **not** hand in a dry document with only figures and code, I'm expecting text before and after each code/graph cell, explaining what you did, why you did it, and how it fits the story you are telling. Don't forget to put labels on your plot axes, title, legend, etc.  

Your Jupyter Notebook should be **fully functional**: if we press `Kernel > Restart & Run All`, all the code must work without any errors.

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