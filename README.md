[![Build Status](https://travis-ci.org/trustedanalytics/space-shuttle-demo.svg)](https://travis-ci.org/trustedanalytics/space-shuttle-demo)
[![Dependency Status](https://www.versioneye.com/user/projects/5723704eba37ce00464e061c/badge.svg?style=flat)](https://www.versioneye.com/user/projects/5723704eba37ce00464e061c)

# space-shuttle-demo
This page summarizes the TAP space shuttle example application. The default version of this application uses Gateway and Kafka as streaming sources. If you want to use mqtt instead, go [here](mqtt/README.md).

## Overview
![](wikiimages/space_shuttle_demo.png)

### Implementation summary
#### Scoring flow:
* The space-shuttle-demo application listens to the Kafka topic and waits for feature vectors.
* When a Kafka message appears, the application asks the Scoring Engine to classify the received feature vector.
* The application stores the scoring result in an InfluxDB database.

#### Generating graph flow:
* The web application asks the backend application (space-shuttle-demo) for an anomalies chart.
* The space-shuttle-demo application fetches anomalies (classes different than 1) several times per minute from InfluxDB and then displays them.

## Analytics Toolkit and spark-tk versions
Two versions of the application are provided:  

- Space Shuttle example application for the *Analytics Toolkit*. Step-by-step instructions for this version are provided [here](https://github.com/trustedanalytics/platform-wiki-0.7/wiki/Space-Shuttle-Example-for-Analytics-Toolkit).
    
- Space Shuttle example application for *spark-tk*. Instructions for this version are currently under development.
