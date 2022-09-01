---
toc: true
layout: post
title: Assignment 2
categories: [markdown]
toc: false
tags: [hydrology]
---

## 📒 Instructions
This is where learning happens, not during a lecture. You'll learn a ton of things by doing them yourself. Much success! 😄

Create a Jupyter Notebook called `assignment-02-IDNUMBER`, where `IDNUMBER` is your 9-digit ID. This is the file only file we will check.

## 📌 Locations and data

**Choose two stations with different climates.**

Go to NOAA's [Climate Reference Network Data](https://www.ncdc.noaa.gov/crn/qcdatasets.html) website. The sub-hourly (5-min) data contains information on
* air temperature,
* precipitation,
* global solar radiation,
* surface infrared temperature,
* relative humidity,
* soil moisture and temperature,
* wetness, and
* 1.5 meter wind speed.

There is no data on air pressure, so one needs to use the stations coordinates (lat, lon) to find its height above sea level, and from that infer the air pressure. You can use Google Earth or any other means to find the station's height.

In the Data Access link, choose a year and a station you would like to analyze. If you are not sure where the stations are, find them using the 2-letter state abbreviation and the station name.

Download the following files:
1. One full year of data for each station. Make sure important data we need to calculate Penman's ET estimation is available.
2. The headers file
3. The documentation file

Make sure you understand what are the units provided for each measurement (see documentation).

## 🛠 Tasks

Produce potential ET estimates using Thornthwaite's equation and Penman's equation.
Produce plots of ET as a function of time for each station, comparing the two methods you used.
Also, using Penman's ET estimates, compare the two stations and discuss about their differences/similarities.

You might find interesting things in the data, such as periods of unusually high/low temperatures, radiation, etc. Discuss how these factors might have affected the ET estimates that you calculated.

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

Below you can find an example of how to import the data file provided by NOAA's Climate Reference Network Data website. You might have to make some adjustments to it.

```python
data_file = "CRNS0101-05-2020-CO_Boulder_14_W.txt"
df = pd.read_csv(data_file,
                 header=None,                      # no headers needed, we'll do that later
                 delim_whitespace=True,            # blank spaces separate between columns
                 na_values=["-99.000", "-9999.0"]  # substitute these values for missing (NaN) values
                )
headers = pd.read_csv("HEADERS_sub_hourly.txt",    # load headers file
                      header=1,                    # skip the first [0] line
                      delim_whitespace=True
                     )
df.columns = headers.columns                       # rename df columns with headers columns
# LST = local standard time
df["LST_TIME"] = [f"{x:04d}" for x in df["LST_TIME"]]  # time needs padding of zeros, then convert to string
df['LST_DATE'] = df['LST_DATE'].astype(str)            # convert date into string
df['datetime'] = df['LST_DATE'] + ' ' + df['LST_TIME'] # combine date+time into datetime
df['datetime'] = pd.to_datetime(df['datetime'])        # interpret datetime
df = df.set_index('datetime')                          # make datetime the index
df
```