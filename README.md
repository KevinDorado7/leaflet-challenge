# leaflet-challenge
Module 15 Challenge

## Description
This project is an interactive map designed to visualize earthquake data from the United States Geological Survey (USGS). The goal is to provide an intuitive and accessible visualization of seismic activity and its relationship with tectonic plates.

## Contents
- `index.html`: The main HTML file that structures the map.
- `static/js/logic.js`: JavaScript file containing functions to fetch data, build the map, and add interactive elements.
- `static/css/style.css`: CSS file to style the map and ensure it fits the screen.
- `README.md`: This file, providing an overview of the project.

## Usage
1. Open the `index.html` file in your preferred web browser.
2. Interact with the map by selecting different base maps and overlays using the layer control.

## Features
- **Interactive Map**: Displays earthquake data with markers that vary in size and color based on magnitude and depth.
- **Tectonic Plates Overlay**: Shows the boundaries of tectonic plates to illustrate their relationship with seismic activity.
- **Layer Control**: Allows users to switch between different base maps (Satellite, Grayscale, Outdoors) and toggle earthquake and tectonic plate data on and off.
- **Popups**: Provides additional information about each earthquake, including its location, magnitude, and depth.
- **Legend**: Displays a color-coded legend indicating the depth of earthquakes.

## Example Usage
1. Open the `index.html` file in your browser.
2. Use the layer control in the top right corner to switch between base maps and to toggle the visibility of the earthquake and tectonic plate layers.
3. Click on earthquake markers to view detailed information about each event.

## Code Snippet Example
In this project, ChatGPT was utilized to generate specific parts of the code and to debug and optimize the code's functionality. For instance, the following code snippet, which creates circle markers for each earthquake and binds a popup with the corresponding information, was generated with the assistance of ChatGPT:

```javascript
earthquakeFeatures.forEach(earthquake => {
  const coordinates = earthquake.geometry.coordinates;
  const properties = earthquake.properties;

  L.circleMarker([coordinates[1], coordinates[0]], {
    radius: getRadius(properties.mag),
    fillColor: getColor(coordinates[2]),
    color: "#000",
    weight: 1,
    opacity: 1,
    fillOpacity: 0.8
  }).bindPopup(`<h3>${properties.place}</h3><hr><p>Magnitude: ${properties.mag}</p><p>Depth: ${coordinates[2]} km</p>`).addTo(earthquakes);
});
