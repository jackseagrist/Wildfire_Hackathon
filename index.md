## Wildfire Hackathon
Project by: Jack Seagrist, Yash Gaur, Hunter Johnson

https://docs.mapbox.com/help/tutorials/#web-apps <-- use this for implementing map box
and the GLJS and SDKs
GLJS: https://docs.mapbox.com/mapbox-gl-js/overview/
Time slider: https://docs.mapbox.com/mapbox-gl-js/example/timeline-animation/

Think about using Arc Webmaps as well: https://doc.arcgis.com/en/arcgis-online/share-maps/embed-maps-groups.htm

### Sample Map


<!--[if gt IE 8]><!--> <html class="no-js"> <!--<![endif]-->
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title></title>
        <meta name="description" content="">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <script src='https://api.mapbox.com/mapbox-gl-js/v1.9.1/mapbox-gl.js'></script>
        <link href='https://api.mapbox.com/mapbox-gl-js/v1.9.1/mapbox-gl.css' rel='stylesheet' />
    </head>
    <style>
        body {
            margin: 0;
            padding: 0;}
    </style>
    <body>
    
        <iframe src='map.html'
            width='100%' height='400px'>

        </iframe>
        
        <iframe src='cartovl.html'
            width='100%' height='400px'>

        </iframe>
        
        <style>.embed-container {position: relative; padding-bottom: 80%; height: 0; max-width: 100%;} .embed-container iframe, .embed-container object, .embed-container iframe{position: absolute; top: 0; left: 0; width: 100%; height: 100%;} small{position: absolute; z-index: 40; bottom: 0; margin-bottom: -15px;}</style><div class="embed-container"><small><a href="//stanford.maps.arcgis.com/apps/Embed/index.html?webmap=30237f6e65a94ae68b677a128fd29b40&extent=-123.5631,37.7588,-121.3054,38.7637&zoom=true&scale=true&search=true&searchextent=true&basemap_gallery=true&disable_scroll=true&theme=light" style="color:#0000FF;text-align:left" target="_blank">View larger map</a></small><br><iframe width="500" height="400" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" title="Wildfire_Tracker" src="//stanford.maps.arcgis.com/apps/Embed/index.html?webmap=30237f6e65a94ae68b677a128fd29b40&extent=-123.5631,37.7588,-121.3054,38.7637&zoom=true&previewImage=false&scale=true&search=true&searchextent=true&basemap_gallery=true&disable_scroll=true&theme=light"></iframe></div>
        
    </body>
</html>

### Project Summary
Our group chose to address problems related to evacuation routes. (have sources here about evacuation routes currently and evacuation plans, research papers). 

To address these problems, our group developed a prototype tool that could be used by fire departments, sheriff departments, and citizens as a central repository of real time fire information to assist with evacuation. We have developed a prototype for a real time fire prediction model that uses the estimated fire path to provide an output of which parts of the jurisdiction should be under which evacuation order: Level 1 Alert, Level 2 Warning, Level 3 Order [1]. Our prototype was developed focusing on California, using historical California wildfire data as inputs to train the model. 
SEE UPDATED PDFS from Scott - now just two levels and a shelter in place order (in outreach folder)

thinks there needs to be a happy medium to get people out of the way and evacuated, but not too early of a full evacuation (leads to evacuation fatigue) or no evacuation at all. Balance (no evac --- happy medium --- full early evac) from Scott

#### Project Scope

(Describe the project here)
Fire prediction
Create circle radius outwards for evacuation
Traffic Layer
Demographic layer to highlight the elderly
Defensible space option - interactive map which allows fire department to locate defended space and send out a tweet
Add Ons:
Us-census layer - people contact info within zones for reverse 911 call
Idea → maybe have a component that allows people to enter the number of resources fighting a fire to influence our model and determine if evacuation is necessary, goes back to getting rid of evacuation fatigue
Have a time component to our layers, to show progression, and have metadata for how long the fire will take to get there

cell phone gps data to know who is still in the area??????? FUture work???

Based on notes with Scott should just focus on 1) Model perimeter prediction- with what the varying perimeters will look like over time 2) estimate evacuation overlay 3) traffic data 4) hospitals, nursing homes, and school locations 5) ability to add in community refuge areas if fire/sheriff dept need to add in

#### Model
Here are some links for some stuff I found for the model. Able to generate perimeters with Flammap 6 software. But someone made a set of python scripts for generating perimeter to webmap, could maybe use that. Also could maybe use outputs from flammap to train AI model. This pdf lists out a lot of the other perimeter prediction softwares as well (Farsite, Nexus, Wi-fire, ArcFuels) http://unigis.sbg.ac.at/files_en/Mastertheses/Full/104195.pdf

Flammap Process
1) download lcp data from Landfire 2) get fuel moisture conditions from https://www.wfas.net/index.php/national-fuel-moisture-database-moisture-drought-103 or https://firesafesanmateo.org/resources/live-fuel-moisture 3) find wind data from that day to use with wind ninja 4) foliar moisture? 5) try to find wtr and wnd files https://www.wunderground.com/history/weekly/us/ca/santa-rosa/KSTS/date/2018-10-25 https://www.meteoblue.com/en/weather/historyclimate/climatemodelled/santa-rosa_united-states-of-america_5393287

Map
Interactive map help https://stackoverflow.com/questions/36581775/mapbox-js-marker-creation-on-click
And think that maybe we can use leaflet.js if need more interactive?
https://paulcrickard.wordpress.com/2012/06/29/leaflet-js-interactivity-ii-allow-users-to-add-points/ --> looks good

#### Future Work
Alert or reference to where hospitals/nursing homes.  And also the number of houses/ population density. Also the time of day will cause different types of evacuation (ask Scott)
What to do for people without cars (we typically assume everyone is able, has a car, speaks english) - research (bodega bay santa rosa). Look into grassroots organizations for illegal immigrant and disabled populations help with evacuation (think about demographic layers)
Something with IPAWS https://www.fema.gov/integrated-public-alert-warning-system ?
Have some sort of public facing side with this as well (or just like a twitter alert)

Map - explore mapbox features with database for users to interact with the map on the fly https://www.mapbox.com/videos/how-to/deploy-a-collaborative-map-with-quick-launch/ https://www.mapbox.com/solutions/quick-launch

Machine Learning - Don't have the time scale data that we need to make model really work. We would need for a single fire the shapefile perimeters at smaller time steps, not just the final perimeter. Then we would have to add in the temporal data somehow. Potentially by making raster values for each datastack where the pixel value is based on the time from ignition

From Scott Westrope - Redundancy. Example is the Tubbs fire where they lost 72 cell towers in 4 hours. Thinking about actual use of the system, it would be good to have it be redundant and still work if towers go down, or if the users are out in the middle of nowhere with no/limited signal (have some type of feature where you can download model based on current/future conditions onto phone and operate that way)

Improved modelling capabilities - talk about what we would need to add in to improve the model. Model predictability should include historical data since fires tend to follow the same path

#### Data
GEE - Data Layers

GeoMAC - historical shape files
Link 1: Determining Fire Dates and Locating Ignition Points With Satellite Data
Link 2: Cal Fire Frap (just perimeters)
Link 3: USDA historical fire
Link 4: InciWeb
Link: Geomac <- think this is the one we used

Descartes Labs - Ignitions


NOT SURE if we used any of this
Town Boundaries:
Link: Cal data
Link: Cal Fire
Link: Who’s on First
Population Data:
https://www.ornl.gov/news/gis-landscan-goes-public
https://geoplatform.maps.arcgis.com/home/item.html?id=e431a6410145450aa56606568345765b
Fire Hazard severity zones:
https://osfm.fire.ca.gov/divisions/wildfire-planning-engineering/wildland-hazards-building-codes/fire-hazard-severity-zones-maps/
Fhszssn
Fire Threat:
https://frap.fire.ca.gov/mapping/gis-data/
US Census Data:
https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-data.html



### Tools

The main tools used to develop this platform were google earth engine, google colaboratory, and Mapbox/Arc WebMap.

### References

[1]. **Descartes Labs** (https://www.descarteslabs.com/)

[2]. Google earth engine

[2]. **Paradise Evacuation Zones** (https://www.townofparadise.com/index.php/17-news-events/248-evacuation-zones)

[2]. Failures of evacuation system Paradis - https://www.pbs.org/wgbh/frontline/article/camp-fire-anniversary-new-details-troubled-evacuation/  && Paradise Vulnerable Populations - https://www.nfpa.org/News-and-Research/Publications-and-media/NFPA-Journal/2019/January-February-2019/News-and-Analysis/Dispatches

[3]. Evacuation Behavior Literature (https://rgs-ibg.onlinelibrary.wiley.com/doi/pdf/10.1002/geo2.51)

[]. California Most Vulnerable Communities Map - (https://www.directrelief.org/2019/07/which-california-communities-are-most-vulnerable-to-wildfires/) -- might be able to incorporate that map with our map if we do arcgis webmaps

[3]. **US Forest Service Evacuation Levels** (https://www.fs.usda.gov/Internet/FSE_DOCUMENTS/stelprd3852749.pdf)

[4]. Cova, Thomas (2019): Geosimulating Hazard Warning Triggers: Geometry, Dynamics, and Timing. The University of Auckland. Conference contribution. https://doi.org/10.17608/k6.auckland.9863267.v1

[] NIST Disaster Failure Studies Fires - https://www.nist.gov/topics/disaster-failure-studies/studies-hazard-types/fires

[] NIST Study of emergency communications during a fire -https://www.nist.gov/el/fire-research-division-73300/wildland-urban-interface-fire-73305/nist-study-emergency

[] NIST community planning resilience guide

[5] ADD REFERENCES FOR GITHUB/CODE WE USED TO START OUR MODEL

### Thank you

We would like to thank the following people for their help in the creation of this project: Derek Fong, Rebecca Miller, Stace Maples, Caitlin Kontgis and the Descarte labs team, Scott Westrope, David Shew, ....
