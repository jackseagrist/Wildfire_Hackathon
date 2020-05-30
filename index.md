## Wildfire Hackathon
Project by: Jack Seagrist, Yash Gaur, Hunter Johnson
 
## Problem Statement

Wildfires pose a significant risk to human life and society, causing an estimated loss of $60-280 billion dollars in 2016 alone in the US with dozens of fatalities each year (1).  Climate and weather directly influence wildfire risks and global warming is expected to further exacerbate fire damage towards natural and urban ecosystems (2).  Just in the past 5 years, 2015-2020, several unprecedented fires have occured in varying parts and ecosystems of California showcasing the needs for new ideas and tools. 

### Motivation

One vital aspect of fire loss prevention is evacuation procedures, in particular how fire and police authorities decide and implement effective yet necessary evacuations in the face of imminent danger.  Aggressive fires, jammed roads, and panicked evacuees can complicate well thought out evacuation procedures potentially having fatal results. Even when a town has preprepared evacuation zone, such as in Paradise, dissemination of information and response in a time sensitive situation can still be extremely difficult (3). Officials attempted to alert the public through the national Integrated Public Alert and Warning System (IPAWS) during the Camp fire but encountered technical difficulties (4).

Our project aims to create an easy to use, government facing, data based tool that assists fire departments in real time evacuation scenarios.  Our tool utilizes live traffic and critical facilities data to provide a blend of need to know data to decision makers in high stake situations.  High human and economic loss fires such as the Camp Fire in Paradise, CA serve as a motivation to help provide information for safe evacuation routes or areas to shelter to minimize wildfire loss. 

### Challenges

Creating a data based live platform has several challenges, most surrounding availability of useful data and its timely implementation.  However, clever integration of online softwares allows a variety of critical variables to be available simultaneously while constantly updating.  Data and technological approaches that fight natural disasters are still nascent but are rapidly evolving, providing a promising future for our platform.

## Project Scope

The scope of our project for this hackathon was to gather stakeholder feedback and create a proof of concept for a potential product. We met with various fire department officials across California as well as industry mentors to identify the critical features that would provide the most benefit in evacuation scenarios. Based on the discussions we've had, there are 5 c

-Basemap - 
-Fire Prediction - showing over time, ability for 
-Evacuation Overlay- 
-Traffic Information - 
-Key Infrastructure - Hospitals, Nursing Homes, and Schools
-Addding Defended Space - 

To address these problems, our group developed a prototype tool that could be used by fire departments, sheriff departments, and citizens as a central repository of real time fire information to assist with evacuation. We have developed a prototype for a real time fire prediction model that uses the estimated fire path to provide an output of which parts of the jurisdiction should be under which evacuation order: Level 1 Alert, Level 2 Warning, Level 3 Order [1]. Our prototype was developed focusing on California, using historical California wildfire data as inputs to train the model. 
SEE UPDATED PDFS from Scott - now just two levels and a shelter in place order (in outreach folder)

thinks there needs to be a happy medium to get people out of the way and evacuated, but not too early of a full evacuation (leads to evacuation fatigue) or no evacuation at all. Balance (no evac --- happy medium --- full early evac) from Scott

### Model

Our initial approach was to use machine learning techniques to develop a model which could predict the fire spread for a given period of time based on open source satellite imagery. However, after initial development we realized due to the complex nature of fire behavior we did not have access to enough data or data with the temporal and spatial resolution required to make an effective model. We switched our approach and began to search for exisiting models and tools that we could use to implement in our prototype. We came across a few model

FlamMap 6 . FlamMap 6 description. how to use it. How we used it in our situation

Here are some links for some stuff I found for the model. Able to generate perimeters with Flammap 6 software. But someone made a set of python scripts for generating perimeter to webmap, could maybe use that. Also could maybe use outputs from flammap to train AI model. This pdf lists out a lot of the other perimeter prediction softwares as well (Farsite, Nexus, Wi-fire, ArcFuels) http://unigis.sbg.ac.at/files_en/Mastertheses/Full/104195.pdf

Flammap Process
1) download lcp data from Landfire 2) get fuel moisture conditions from https://www.wfas.net/index.php/national-fuel-moisture-database-moisture-drought-103 or https://firesafesanmateo.org/resources/live-fuel-moisture 3) find wind data from that day to use with wind ninja 4) foliar moisture? 5) try to find wtr and wnd files https://www.wunderground.com/history/weekly/us/ca/santa-rosa/KSTS/date/2018-10-25 https://www.meteoblue.com/en/weather/historyclimate/climatemodelled/santa-rosa_united-states-of-america_5393287

### Map

The second critical component to our evacuation management tool is the final display of the predicted outputs. We investigated using both Mapbox and ArcGIS Webmaps. Went with ArcGIS Webmaps

## Prototype

Describe what we envision the user experience to be, ending with the link to the prototype.

[a relative link](tracker_start.md)
[a relative link](map.html)
[a relative link](map3.html)
[Prototype](/template/index2.html)

## Future Work

The following sections describe the work needed to take this project from a concept to a viable product.

### Model

Machine Learning - Don't have the time scale data that we need to make model really work. We would need for a single fire the shapefile perimeters at smaller time steps, not just the final perimeter. Then we would have to add in the temporal data somehow. Potentially by making raster values for each datastack where the pixel value is based on the time from ignition

Improved modelling capabilities - talk about what we would need to add in to improve the model. Model predictability should include historical data since fires tend to follow the same path

Models really need analysts right now to tweak parameters and make the models accurate, because even if you put in what you think are the parameters that represent the region
SB example - if you use the shrub model for fuel, the fire never moves as fast as it does in real life. Need to select grass even though it is shrubs over there. Only would know that with experience in that area
Need the analyst to explain the outputs

Attached to the email is a screen shot showing the models we typically use to support incidents, an overview of WFDSS and the modeling support embedded within the site, and a guide to the use of Fire Behavior Fuel Models that are used in the models.

### Automation

Making a pipeline that automatically generates prototype outputs

### Licensing

Stace mentioned a lot of places use esri, but if they don't have a liscense then wouldn't be able to accesss. Think about Mapbox as an alternative

### Dissemination to the Public

Right now the focus on our tool has been to help fire and sheriff's departments with their evacuation management.
Alert or reference to where hospitals/nursing homes.  And also the number of houses/ population density. Also the time of day will cause different types of evacuation (ask Scott)
What to do for people without cars (we typically assume everyone is able, has a car, speaks english) - research (bodega bay santa rosa). Look into grassroots organizations for illegal immigrant and disabled populations help with evacuation (think about demographic layers)
Something with IPAWS https://www.fema.gov/integrated-public-alert-warning-system ?
Have some sort of public facing side with this as well (or just like a twitter alert)

Map - explore mapbox features with database for users to interact with the map on the fly https://www.mapbox.com/videos/how-to/deploy-a-collaborative-map-with-quick-launch/ https://www.mapbox.com/solutions/quick-launch

### Redundancy

From Scott Westrope - Redundancy. Example is the Tubbs fire where they lost 72 cell towers in 4 hours. Thinking about actual use of the system, it would be good to have it be redundant and still work if towers go down, or if the users are out in the middle of nowhere with no/limited signal (have some type of feature where you can download model based on current/future conditions onto phone and operate that way)

## Data

1. National Interagency Fire Center (NIFC) FTP server[] - GIS data generated from Incident teams including fire points, fire perimeter, and fire polygons.

2. Environmental Systems Research Institute (ESRI) data layers [] - ESRI generates data layers which are accessible via their webmaps. Our project included layers for Nursing Homes, Hospitals, School location, and Traffic.

## Tools

1. ArcGIS Web Map - ArcGIS Web Maps was used to prototype the final map output for the fire evacuation management tool. 

2. FlamMap 6 - Desktop application that is used to simulate fire behavior. Includes FARSITE (Finney 1998, 2004) and FlamMap BASIC (Finney 2006), Minimum Travel Time (MTT, Finney 2002, 2006), Treatment Optimization Model (Finney 2001, 2006, 2007), and Conditional Burn Probability (Finney 2005, 2006).

## References

[1] Keely and Sephard 2016, 'Climate Change and Future Fire Regimes: Examples From California", Geosciences 6(3), 37.

[2] Thomas et al. 2017, 'The Costs and Losses of Wildfires', National Institute of Standards and Technology.

[3] Paradise Evacuation Zones(https://www.townofparadise.com/index.php/17-news-events/248-evacuation-zones).

[4] Zoe Todd Sydney Trattner Jane McMullen, "Ahead of Camp Fire Anniversary, New Details Emerge of Troubled Evacuation (https://www.pbs.org/wgbh/frontline/article/camp-fire-anniversary-new-details-troubled-evacuation/).




[1]. **Descartes Labs** (https://www.descarteslabs.com/)

[2]. Google earth engine



  && Paradise Vulnerable Populations - https://www.nfpa.org/News-and-Research/Publications-and-media/NFPA-Journal/2019/January-February-2019/News-and-Analysis/Dispatches

[3]. Evacuation Behavior Literature (https://rgs-ibg.onlinelibrary.wiley.com/doi/pdf/10.1002/geo2.51)

[]. California Most Vulnerable Communities Map - (https://www.directrelief.org/2019/07/which-california-communities-are-most-vulnerable-to-wildfires/) -- might be able to incorporate that map with our map if we do arcgis webmaps

[3]. **US Forest Service Evacuation Levels** (https://www.fs.usda.gov/Internet/FSE_DOCUMENTS/stelprd3852749.pdf)

[4]. Cova, Thomas (2019): Geosimulating Hazard Warning Triggers: Geometry, Dynamics, and Timing. The University of Auckland. Conference contribution. https://doi.org/10.17608/k6.auckland.9863267.v1

[] NIST Disaster Failure Studies Fires - https://www.nist.gov/topics/disaster-failure-studies/studies-hazard-types/fires

[] NIST Study of emergency communications during a fire -https://www.nist.gov/el/fire-research-division-73300/wildland-urban-interface-fire-73305/nist-study-emergency

[] NIST community planning resilience guide

[5] ADD REFERENCES FOR GITHUB/CODE WE USED TO START OUR MODEL

[] https://www.nifc.gov/

[] https://www.esri.com/en-us/home



## Thank you

We would like to thank the following people for their help in the creation of this project: Derek Fong, Rebecca Miller, Stace Maples, Caitlin Kontgis and the Descartes labs team, Scott Westrope, David Shew, Nic Elmquist, and all of the other hackathon teams!
