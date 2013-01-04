# Simple Map (D3)

A very simple "choropleth" style map with tooltips with D3 (R2D3).  All you need is a GeoJSON of polygons.

## Data

Any latitude and longitude based GeoJSON file will work.

## Basic Usage

Include JS
  
    <script type="text/javascript" src="http://d3js.org/d3.v3.min.js"></script>
    <script type="text/javascript" src="js/simple-map-d3.js"></script>

Create container

    <div id="simple-map-d3-example"></div>
    
Create the map

    var map = new SimpleMapD3({
      container: '.simple-map-d3-example',
      datasource: 'data/mn-county-2010.json'
    });

## Options

The following are options that can be passed to the SimpleMapD3 object
when creating it:

* ```container```: The DOM selector for the DOM element that will hold the map.  REQUIRED.
  * Data type: string
* ```datasource```: String location of json file to use.  REQUIRED.
  * Data type: string
* ```colorOn```: Whether to process fill colors.  Use with ```colorSet``` and ```colorProperty```.
  * Data type: boolean
  * default: ```false```
* ```colorSet```: An array of valid color strings.
  * Data type: array
  * default: Array of green colors from [ColorBrewer.org](http://colorbrewer2.org/)
* ```colorProperty```: The property that will be used to determine the fill color.  This is a property found in the ```properties``` object of each feature in the GeoJSON file.  This will depend on your data.
  * Data type: string
* ```colorStep```: The step to use for the color range.
  * Data type: numerical
  * Default: determined from the minimum and maximum of the color property data.

## API

For other data sources, like JSONP data, you can directly hand the data
to the map like so:

    var map = new SimpleMapD3({
      container: '.simple-map-d3-example',
      data: yourOwnDataVariable
    });