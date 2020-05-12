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
        
        <style>.embed-container {position: relative; padding-bottom: 80%; height: 0; max-width: 100%;} .embed-container iframe, .embed-container object, .embed-container iframe{position: absolute; top: 0; left: 0; width: 100%; height: 100%;} small{position: absolute; z-index: 40; bottom: 0; margin-bottom: -15px;}</style><div class="embed-container"><small><a href="//arcgis.com/apps/Embed/index.html?webmap=30237f6e65a94ae68b677a128fd29b40&extent=-132.7947,29.2025,-81.0272,49.705&zoom=true&scale=true&disable_scroll=true&theme=light" style="color:#0000FF;text-align:left" target="_blank">View larger map</a></small><br><iframe width="500" height="400" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" title="LANDFIRE_Topography" src="//arcgis.com/apps/Embed/index.html?webmap=30237f6e65a94ae68b677a128fd29b40&extent=-132.7947,29.2025,-81.0272,49.705&zoom=true&previewImage=false&scale=true&disable_scroll=true&theme=light"></iframe></div>
        
    </body>
</html>

### Project Summary
Our group chose to address problems related to evacuation routes. (have sources here about evacuation routes currently and evacuation plans, research papers). 

To address these problems, our group developed a prototype tool that could be used by fire departments, sheriff departments, and citizens as a central repository of real time fire information to assist with evacuation. We have developed a prototype for a real time fire prediction model that uses the estimated fire path to provide an output of which parts of the jurisdiction should be under which evacuation order: Level 1 Alert, Level 2 Warning, Level 3 Order [1]. Our prototype was developed focusing on California, using historical California wildfire data as inputs to train the model.

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


### Tools

The main tools used to develop this platform were google earth engine, google colaboratory, and Mapbox/Arc WebMap.

### References

[1]. **Descartes Labs** (https://www.descarteslabs.com/)
[2]. **Paradise Evacuation Zones** (https://www.townofparadise.com/index.php/17-news-events/248-evacuation-zones)
[3]. **US Forest Service Evacuation Levels** (https://www.fs.usda.gov/Internet/FSE_DOCUMENTS/stelprd3852749.pdf)
[4]. 

### Thank you

We would like to thank the following people for their help in the creation of this project: Derek Fong, Rebecca Miller, Stace Maples, Caitlin Kontgis and the Descarte labs team, Scott Westrope, David Shew, ....

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
