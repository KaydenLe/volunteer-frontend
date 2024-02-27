---
permalink: /maps
layout: base
title: maps
---
<html style="height: 100%; margin: 0; padding: 0;">
<head>
  <title>Volunteer Map</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-color: #E3DAC9;
    }
    #map-container {
      height: 80vh; /* Adjust height as needed */
      width: 80%; /* Adjust width as needed */
      margin: 20px auto; /* Center the map horizontally */
      border: 2px solid #ccc; /* Add border */
      border-radius: 10px; /* Optional: Add border radius */
    }
    #map {
      height: 100%;
      width: 100%;
    }
    header {
      background-color: #E3DAC9; /* Set background color for the header */
      color: white; /* Set text color for the header */
      padding: 10px 0; /* Add padding to the header */
      text-align: center; /* Center align text within the header */
    }
  </style>
<body>
  <header>
    <h1>Volunteer Map</h1>
  </header>
  <!--The div element for the map -->
  <div id="map-container">
    <div id="map"></div>
  </div>
</body>
  <script src="https://polyfill.io/v3/polyfill.min.js?features=default"></script>
  <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyC9pEqmLuhD8-W86bZHiuDpCgeXlCoxVTc&callback=initMap"
  async defer></script>
  <script type="text/javascript">
    let map;
    async function initMap() {
      map = new google.maps.Map(document.getElementById("map"), {
        center: { lat: 37.0902, lng: -95.7129}, // Centered of America
        zoom: 4, // Adjust the zoom level as needed
        styles: [] // Remove custom styles
      });
      const markers = [
        {lat:32.7528, lng: -117.0891, label: 'San Diego Refugee Tutoring'}, //4877 Orange Ave, San Diego, CA 92115
        {lat:33.120540, lng: -117.080310, label: 'Youth Court'}, //220 S Broadway, Escondido, CA 92025
        {lat:32.731602, lng: -117.147850, label: 'Balboa Natural History Museum'}, //1788 El Prado, San Diego, CA 92101
        {lat:34.042060, lng: -118.234790, label: 'Step Up'}, //510 South Hewitt Street #111 Los Angeles, CA 90013
        {lat:37.815840, lng: -122.268710, label: 'Children Rising'}, //2633 Telegraph Avenue #412
        {lat:47.6383529, lng: -122.3765739, label: 'Seattle Animal Shelter'}, //2061 15th Ave W, Seattle, WA, 98119
        {lat:40.725719, lng: -74.003738, label: 'God’s Love We Deliver'}, //166 Avenue of the Americas
        {lat:29.8415611, lng: -81.3669855, label: 'Horse Play Therapy Center'}, //1925 State Road 207 Saint Augustine, FL 32086
        {lat:42.3176586, lng: -71.1027539, label: 'Community Servings Food Heals'}, //179 Amory Street Jamaica Plain, MA 02130
        {lat:41.8832522, lng: -87.6518247, label: 'Emmaus'}, //954 W. Washington Blvd
        // Add markers for the remaining addresses following the same format...
      ];
      // Add markers to the map
      markers.forEach(marker => {
        const newMarker = new google.maps.Marker({
          position: marker,
          map: map,
          title: marker.label // Display label as marker title
        });
        // Add click event listener to the marker
        newMarker.addListener('click', function() {
          alert('Place: ' + marker.label + '\nLatitude: ' + this.getPosition().lat() + '\nLongitude: ' + this.getPosition().lng());
        });
      });
    }
  </script>
</head>
<body>
  <!--The div element for the map -->
  <div id="map-container">
    <div id="map"></div>
  </div>
</body>
</html>









