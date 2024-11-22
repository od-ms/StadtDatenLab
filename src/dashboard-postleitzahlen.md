---
theme: dashboard
title: Postleitzahlen Karte
toc: false
---

# Postleitzahlen

## Dashboard-Darstellungsmöglichkeiten mit Observable Notebooks

## Als interaktive Karte mit Leaflet


```js
import * as L from "npm:leaflet";

const plz = FileAttachment("data/plz-muenster.geojson").json();
```

```js
const div = display(document.createElement("div"));
div.style = "height: 600px;";

const map = L.map(div)
  .setView([51.505, -0.09], 13);

L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png", {
  attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>'
})
  .addTo(map);

let grandCentralLayer = L.geoJson(plz, {
weight: 2,
color: '#f77'
}).addTo(map);

map.fitBounds(grandCentralLayer.getBounds());

```

## Postleitzahlen als Plot


```js

const fills = {
    48249: "#333",
    48301: "#666",
    48157: "#999",

}

display(Plot.plot({
  width: 688,
  height: 688,
  marks: [
    Plot.geo(
        plz,
        {stroke: "white",
        fill: (d) => (d.properties.postal_code in fills ? fills[d.properties.postal_code] : "grey")}
    ), // Add county boundaries using the geo mark
    Plot.text(
      plz.features,
      Plot.centroid({
        text: (d) => d.properties.postal_code,
        textAnchor: "middle",
        stroke: "darkred",
        fill: "yellow"
      })
    )
]
}))


```

Anleitung:
* Speziell Choroplethen: https://observablehq.com/@observablehq/build-your-first-choropleth-map-with-observable-plot
* Sehr gute Beispiele: https://observablehq.com/@observablehq/plot-mapping
* Siehe auch die Beispiele hier: https://github.com/tannerlinsley/observable-plot/blob/main/CHANGELOG.md

Weitere evtl brauchbare Links:
* https://stackoverflow.com/questions/14492284/center-a-map-in-d3-given-a-geojson-object
* https://observablehq.com/plot/features/projections
* https://observablehq.com/@sto3psl/map-of-germany-in-d3-js
* Hammer krass: https://observablehq.observablehq.cloud/framework-example-us-dams/
