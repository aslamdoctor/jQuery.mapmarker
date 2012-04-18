jQuery Map Marker Plugin 1.0.0

Step-1 : Include necessary JS files in your <head> tag

<script type="text/javascript" src="http://code.jquery.com/jquery-1.7.1.min.js"></script>
<script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?sensor=false"></script>

<script type="text/javascript" src="js/mapmarker.jquery.js"></script>

--------------------------------------------------------------------

Step-2 : Create a Map container using & give it an ID in your html body

<div id="map" style="width: 550px; height: 450px; border:2px solid red;"></div>

--------------------------------------------------------------------

Step-3 : Apply the Plugin to the Map element using below code. Put the code before closing your </head> tag

<script type="text/javascript">
	// Use below link if you want to get latitude & longitude
	// http://www.findlatitudeandlongitude.com/find-address-from-latitude-and-longitude.php
	
	$(document).ready(function(){
	
		//set up markers 
		var myMarkers = {"markers": [
				{"latitude": "31.42866311735861", "longitude":"-98.61328125", "icon": "img/house.png", "baloon_text": 'This is <strong>Texas</strong>'},
				{"latitude": "35.101934057246055", "longitude":"-96.6796875", "icon": "img/castle.png", "baloon_text": 'This is <strong>Oklahoma</strong>'},
				{"latitude": "38.61687046392973", "longitude":"-98.876953125", "icon": "img/house.png", "baloon_text": 'This is <strong>Kansas</strong>'}
			]
		};
		
		//set up map options
		$("#map").mapmarker({
			zoom	: 5,
			center	: 'United States',
			markers	: myMarkers
		});

	});
</script>

In the code above, I have added a Link which will get you get the Latitude & Longitude co-ordinates of any specific location.
myMarker : We have used this variable to store JSON data of each locations. Each locations will include 4 entities.
1. latitude - latitude of the location
2. longitude - longitude of the location
3. icon - a custom icon to display on map as marker (16 x 16 pixels size)
4. baloon_text - a Text to display in a Baloon on map when clicked on that specific Marker. You can also use this text in HTML format. Make sure you use single quotes(') only for HTML format baloon text.

Additionally, there are 2 more options which you can set on Map.
1. zoom - to set default zoom level of the Map. Increase the value to zoom-in & Decrease the value to zoom-out
2. center - to specify the center location of the Map. Make sure the center location address you enter is spelled properly.
3. markers - this will be simply the Markers variable we created, here it is "myMarkers"

--------------------------------------------------------------------

Step-4 : That's All