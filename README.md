# Let's make an web map

## Step 1

Create a "map" folder on your desktop, or desired location on your computer. This is where you will save files for this workshop.

## Step 2

Open VSCode.

If you do not have VSCode, you can download it here:

   - [VSCode](https://code.visualstudio.com/download)

## Step 3

1. Click "Open Folder"
1. Navigate to your "map" folder you created in Step 1
1. Click on the "new file" button as shown below:

<img src="images/vscode start.png" width=400>

4. Name the file "map.html"

Your VSCode should now look like this:

<img src="images/map file.png" width=400>

## Step 3

Copy and paste the following code::

```html
<!-- leaflet css -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />

<!-- leaflet javascript -->
<script src="https://unpkg.com/leaflet@1.4.0/dist/leaflet.js"></script>

<!-- the map container -->
<div id="map" style="width: 100%; height: 600px;"></div>

<!-- the javascript to make the map -->
<script>
	// location
	var latlon = [35.6585, 139.7454]

	// create the map
	var map = L.map('map').setView(latlon, 18);

	// add a basemap
	L.tileLayer('https://cyberjapandata.gsi.go.jp/xyz/seamlessphoto/{z}/{x}/{y}.jpg', {
		attribution: '国土地理院'
	}).addTo(map);

	// add a marker with a popup window
	L.marker(latlon).addTo(map)
		.bindPopup("Tokyo Tower")
		.openPopup();
</script>

```

## Step 4

Save the file. Find the file `map.html` on your desktop (or the location you chose to use) and double click it.

## Step 5

Customize the map. Find the latitude and longitude of a location on earth.

Go to google maps: https://www.google.com/maps

Search or navigate to any location.

Right click, and select the coordinates (it will automatically be copied to your clipboard)

![coords](https://user-images.githubusercontent.com/825990/185029320-c394fea6-28d1-4b15-bfa8-ec7f179e1aaf.png)

## Step 6

Replace the latitude and longitude coordinates in the code with the numbers you just copied from Google Maps.

## Step 7

Some challenge exercises:

- Add a title and description (use HTML tags `<h1></h1>`, `<p></p>`)
- Change the text in the popup window
- Add multiple markers to the map
- Add a circle to the map (example below, radius is in pixels)

```
// add a circle 
L.circleMarker([latitude,longitude],{radius:100}).addTo(map)
```

Guides:

- https://python-visualization.github.io/folium/latest/getting_started.html
- https://qiita.com/Kumanuron-1910/items/12ce7aa02922927de2f4
  
## Discussion

- Explain what you have just created, and why it may or may not be useful
- How is an "interactive" map *different*?
- Discuss additional features you would like to add to your map
- Elaborate on how this type of data visualization (i.e. map-based) can be used in your field of interest

