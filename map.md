---
layout: map-page
title: "Map"
permalink: /map/
author_profile: true
---

<div id="mapid"></div>
<script>
var mymap = L.map('mapid').setView([40.7128, -74.0060], 13); // New York City

// Add Stamen Watercolor tile layer
L.tileLayer('https://stamen-tiles-{s}.a.ssl.fastly.net/watercolor/{z}/{x}/{y}.jpg', {
    attribution: 'Map tiles by Stamen Design, CC BY 3.0 - Map data © OpenStreetMap contributors, CC-BY-SA',
    maxZoom: 18,
}).addTo(mymap);

// Function to convert CSV to GeoJSON (from Step 3)
function csvToGeoJSON(csvString) {
    // Conversion code here...
}

// Fetch data and add to map (from Step 4)
fetch('https://docs.google.com/spreadsheets/d/1j-2yi_4xlJpI-f_hNCy4R580aLNDxschVwr0dBgIhHQ/edit?usp=sharing')
    .then(response => response.text())
    .then(csvString => {
        const geojsonData = csvToGeoJSON(csvString);
        L.geoJSON(geojsonData, {
            pointToLayer: function (feature, latlng) {
                return L.circleMarker(latlng); // This creates a simple circle marker for each point
            }
        }).addTo(mymap);
    })
    .catch(error => {
        console.error('Error loading the data: ', error);
    });
</script>
