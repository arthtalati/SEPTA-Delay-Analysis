# SEPTA-Delay-Analysis
Analysed SEPTA on-time-performance for Kaggle Data


# Introduction

Approximately 119,000 daily riders take advantage SEPTA’s Regional Rail system, which provides service to the Philadelphia metropolitan area. The SEPTA (Southeastern Pennsylvania Transportation Authority) Regional Rail system consists of commuter rail service on 13 branches to more than 150 active stations in Philadelphia, Pennsylvania, and its suburbs and satellite cities.


SEPTA reports On-Time Performance (OTP) to measure service reliability. OTP identifies the number of trains for all rail lines that arrive at their scheduled destination at the scheduled time. However, by industry standard, a train may arrive up to 5 minutes and 59 seconds after its scheduled time and still be considered on-time. SEPTA has set an On-Time Performance target such that 91% of its trains arrive on time. Thus, even with 100% “on time” performance, trains may still arrive late, forcing commuters to deal with uncertainty and lost time – especially if they rely on back-to-back connections.


The blue lines in the map show all the regional rail line of SEPTA. (image from google maps)

![Image](http://drive.google.com/uc?export=view&id=1x37x4B9RxtBsgRWhYzVg7dLZR8FcKQVW)


## TWINT API

[Twint](https://github.com/twintproject/twint) is an advanced Twitter scraping tool written in Python that allows for scraping Tweets from Twitter profiles without using Twitter's API. I used this tool to get all tweets from [@SEPTA](https://twitter.com/SEPTA), i.e. SEPTAs official twitter account.


## Philly Weather data
Found [data](https://www.ncdc.noaa.gov/cdo-web/search), to provide me with weather data for Philly of 2016.

## Kaggle data

Kaggle had two csv files for ths dataset otp.csv and trainView.csv

This “otp.csv” from the Kaggle dataset contains On-Time Performance information as from 23 March, 2016 to 6 November, 2016 :


*   train_id
*   direction ('N' or 'S' direction is demarcated as either Northbound or Southbound)
*   origin ('Warminster', 'Glenside',...'Airport Terminal..')
*   next_station (Think of this as the station stop, at timeStamp)
*   date
*   status ('On Time', '5 min', ... This is a status on train lateness. 999 is a suspended train)
*   timeStamp

Note as per the dataset, only 32% of trains run perfectly “on-time”, with another 30% running 1-3 minutes late and the remaining ~1/3 of the trains running >3 minutes late

trainView.csv - GPS Train data (early release)

GPS coordinates are based on track telemetry.

  * train_id
  * status
  * next_station
  * service
  * dest
  * lon
  * lat
  * source
  * track_change
  * track
  * date
  * timeStamp0 First timeStamp at coordinates.
  * timeStamp1 Last timeStamp at coordinates.


## Machine Learning

I determine the delays in the OPT dataset. We could combine weather data with the on-time performance data and see its effect too. The aim of this section would be to be able to predict the delays in the SEPTA regional rail system.
The machine learing results provide a strong case for predicting future delays for regional rail lines
