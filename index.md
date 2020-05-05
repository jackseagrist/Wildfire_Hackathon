## Wildfire Hackathon
https://docs.mapbox.com/help/tutorials/#web-apps <-- use this for implementing map box
You can use the [editor on GitHub](https://github.com/jackseagrist/Wildfire_Hackathon/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Sample Map
<!DOCTYPE html>

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

        #map {
            position: absolute;
            top: 0;
            bottom: 0;
            width: 100;
            }
    </style>
    <body>
        <div id='map'></div>
        <script>
            
            mapboxgl.accessToken = 'pk.eyJ1IjoiamtzZWFncmlzdCIsImEiOiJjazlpNHkzaG4xNWJ1M2ZvNHJuajh2ZXRhIn0.rFXMJ_jmruGL11vxChintQ';
            var map = new mapboxgl.Map({
            container: 'map', // container id
            style: 'mapbox://styles/jkseagrist/ck9tj1z960j5h1in1zqeh4xq7', // replace this with your style URL 
            center: [-54.643, -12.472],
            zoom: 3 
          });

          // disable map zoom when using scroll
            map.scrollZoom.disable();
        </script>
      
    </body>
</html>

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

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/jackseagrist/Wildfire_Hackathon/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
