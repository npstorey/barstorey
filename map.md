---
layout: map-page
title: "Map"
permalink: /map/
author_profile: true
---

<div id="mapid" style="height: 400px;"></div>
<script>
var mymap = L.map('mapid').setView([51.505, -0.09], 13); // Set the initial position and zoom level of the map

L.tileLayer('https://stamen-tiles-{s}.a.ssl.fastly.net/watercolor/{z}/{x}/{y}.jpg', { // Use Stamen Watercolor map tiles
    attribution: 'Map tiles by <a href="http://stamen.com">Stamen Design</a>, <a href="http://creativecommons.org/licenses/by/3.0">CC BY 3.0</a> &mdash; Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>',
    maxZoom: 18,
}).addTo(mymap);

// Add markers or other elements here
</script>
