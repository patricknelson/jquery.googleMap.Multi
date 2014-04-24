jquery.googleMap.Multi
======================

Updated Google Maps API for multiple locations.

## Usage: ##

**Note:** See the [Google Maps JS API documentation](https://developers.google.com/maps/documentation/javascript/styling?csw=1) for more information on using styles.

	$(function() {
	    $(".map").googleMap({
			// Options: "roadmap", "satellite", "hybrid" or "terrain".
			mapType: "roadmap",
			
			// URL to file containing JSON encoded data on map points.
	    	url: "data.json",

			// Map Styles. See the Google Maps JS API documentation for more information on using styles.
			// https://developers.google.com/maps/documentation/javascript/styling
	    	styles: [
				{
					"featureType": "landscape",
					"stylers": [
						{
							"color": "#efefef"
						}
					]
				}
			]
	    });
	
	});

## Example JSON Data: ##

The JSON below allows you to define define a set of points. You can provide multiple sets and then indicate which set (via "initialset") should be displayed first.

	{
		"initialset": "set1",
		"sets": [
			{
				"setid": "set1",
				"bounds": null,
				"points": [
					{
						"latlng": ["32.2926", "-64.7822"],
						"content": "<strong>Example Title 1<\/strong><br \/>Example Text 1",
						"icon": "images/icon.png",
						"zoom": "10"
					}
				]
			},
			{
				"setid": "set2",
				"bounds": null,
				"points": [
					{
						"latlng": ["40.7146", "-74.0066"],
						"content": "<strong>Example Title 2<\/strong><br \/>Example Text 2",
						"icon": "images/icon.png",
						"zoom": "10"
					}
				]
			}
		]
	}

**Note:** Currently there is no way to customize how to switch between sets of map points (an API to do this will need to be done, see `TODO` below). For now, use the example code below to define the buttons used to switch between each set.

    <a id="set1" class="set" href="javascript:;">Set 1</a>
    <a id="set2" class="set" href="javascript:;">Set 2</a>


## TODO: 

* Define an API to allow switching between each set.