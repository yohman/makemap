# Let's make an interactive map

## Step 1

Open a text editor. Any editor will do.

- Mac: TextEdit
- PC: Notepad

## Step 2

If using TextEdit (Mac), make sure you are in plain text mode.

<img width="430" alt="makeplain" src="https://user-images.githubusercontent.com/825990/185028370-06850ed7-e680-43b4-8061-60c06d74db15.png">

## Step 3

Copy and paste the following code into your text editor:

```html
<!-- leaflet css -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.4.0/dist/leaflet.css" integrity="sha512-puBpdR0798OZvTTbP4A8Ix/l+A4dHDD0DGqYW6RQ+9jxkRFclaxxQb/SJAWZfWAkuyeQUytO7+7N4QKrDh+drA==" crossorigin=""/>

<!-- leaflet javascript -->
<script src="https://unpkg.com/leaflet@1.4.0/dist/leaflet.js" integrity="sha512-QVftwZFqvtRNi0ZyCtsznlKSWOStnDORoefr1enyq5mVL4tmKB3S/EnC3rRJcxCPavG10IcrVGSmPh6Qw5lwrg==" crossorigin=""></script>

<!-- the map container -->
<div id="map" style="width: 800px; height: 600px;"></div>

<!-- the javascript to make the map -->
<script>
	// create the map
	var map = L.map('map').setView([35.7426941,139.9062533], 16);

	// add a basemap
	L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
		attribution: '© <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
	}).addTo(map);

	// add a marker with a popup window
	L.marker([35.7426941,139.9062533]).addTo(map)
		.bindPopup("Don't fall asleep! Mapping is fun!")
		.openPopup();
</script>
```

## Step 4

Save the file as `map.html` on your desktop (or preferred location on your computer). Find the file and double click it.

## Step 5

Customize the map. Find the latitude and longitude of a location on earth.

Go to google maps: https://www.google.com/maps

Search or navigate to any location.

Right click, and select the coordinates (it will automatically be copied to your clipboard)

![coords](https://user-images.githubusercontent.com/825990/185029320-c394fea6-28d1-4b15-bfa8-ec7f179e1aaf.png)

## Step 6

Replace the latitude and longitude coordinates in the code with the numbers you just copied from Google Maps.

Hint: There are *two* places you will need to change.

## Step 7

Some challenge exercises:

- Change the text in the popup window
- Add multiple markers to the map
- Add a circle to the map (example below, radius is in pixels)

```
// add a circle 
L.circleMarker([latitude,longitude],{radius:100}).addTo(map)
```

