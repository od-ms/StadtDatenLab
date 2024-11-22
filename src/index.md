---
toc: false
---

<div class="hero">
  <h1>StadtDatenLab Münster</h1>
  <h2>Datenvisualisierung mittels Observable Notebooks</h2>
  <a href="https://observablehq.com/framework/getting-started">"Get started" Doku<span style="display: inline-block; margin-left: 0.25rem;">↗︎</span></a>
</div>


<div class="grid grid-cols-1">
  <div class="big card">
Hier soll ein Internetangebot entstehen, das Daten aus der Stadt Münster visualisiert. Es soll möglich sein, Visualisierungen in Form von Diagramme, Karten und Graphen abzurufen. Besucher*innen sollen städtische Daten erkunden, anschauen und prüfen können. Ein niederschwellig zugänglicher Faktencheck soll ermöglicht werden.
  </div>
</div>


---

## Informationen zu Observable Notebooks

Links zu Observable Dokumentation:

* Observable Framework Doku https://observablehq.com/framework/
* Observable Plot Dokumentation https://observablehq.com/plot/transforms/group
* D3 Funktionen bei Observable https://observablehq.com/@d3/d3-ascending
* D3 Funktionen bei D3JS https://d3js.org/d3-array/summarize
* Code Beispiele: https://github.com/observablehq/framework/blob/main/examples/

Vorteile von Observable:

* Lässt sich in statische HTML Seiten kompilieren und als statische Seiten deployen - keine speziellen Server zum Hosten der Notebooks sind notwendig - Hosting auf Github Pages möglich
* Entwicklung dynamisch wie bei Juypter Notebooks, in gängigen (Web-)Programmiersprachen: Javascript, Markdown, Html
* Eingebaute Unterstützung von D3.js mit Datenmanipulations- und Visualisierungsfunktionen. Große Beispielbibliothek. Möglichkeit zur Nutzung aller Visualisierungsbibliotheken aus dem Javascript-Universum. Datenimporter in allen Programmiersprachen möglich.
* Open Source, große Community

Nachteile: ?

---

## Ideen zur Umsetzung der Visualisierungsplattform

Alle DatenDateien sollten Frictionless DataPackage-Beschreibungen erhalten:
* https://datapackage.org/standard/data-package/

Ideen für Namen:

* StadtDatenHub
* DatenChecker
* FaktenFinder
* DatenNavigator
* DatenAtlas
* StadtDatenLab
* DatenKompass
* DatenExplorer
* DatenRadar
* DatenLabor
* OpenVis
* OpenDataWelt
* InfoAtlas
* DatenBuddy


## Beispieldiagramme

<div class="grid grid-cols-2" style="grid-auto-rows: 504px;">
  <div class="card">${
    resize((width) => Plot.plot({
      title: "Your awesomeness over time 🚀",
      subtitle: "Up and to the right!",
      width,
      y: {grid: true, label: "Awesomeness"},
      marks: [
        Plot.ruleY([0]),
        Plot.lineY(aapl, {x: "Date", y: "Close", tip: true})
      ]
    }))
  }</div>
  <div class="card">${
    resize((width) => Plot.plot({
      title: "How big are penguins, anyway? 🐧",
      width,
      grid: true,
      x: {label: "Body mass (g)"},
      y: {label: "Flipper length (mm)"},
      color: {legend: true},
      marks: [
        Plot.linearRegressionY(penguins, {x: "body_mass_g", y: "flipper_length_mm", stroke: "species"}),
        Plot.dot(penguins, {x: "body_mass_g", y: "flipper_length_mm", stroke: "species", tip: true})
      ]
    }))
  }</div>
</div>

---

## Next steps

Here are some ideas of things you could try…

<div class="grid grid-cols-4">
  <div class="card">
    Chart your own data using <a href="https://observablehq.com/framework/lib/plot"><code>Plot</code></a> and <a href="https://observablehq.com/framework/files"><code>FileAttachment</code></a>. Make it responsive using <a href="https://observablehq.com/framework/javascript#resize(render)"><code>resize</code></a>.
  </div>
  <div class="card">
    Create a <a href="https://observablehq.com/framework/project-structure">new page</a> by adding a Markdown file (<code>whatever.md</code>) to the <code>src</code> folder.
  </div>
  <div class="card">
    Add a drop-down menu using <a href="https://observablehq.com/framework/inputs/select"><code>Inputs.select</code></a> and use it to filter the data shown in a chart.
  </div>
  <div class="card">
    Write a <a href="https://observablehq.com/framework/loaders">data loader</a> that queries a local database or API, generating a data snapshot on build.
  </div>
  <div class="card">
    Import a <a href="https://observablehq.com/framework/imports">recommended library</a> from npm, such as <a href="https://observablehq.com/framework/lib/leaflet">Leaflet</a>, <a href="https://observablehq.com/framework/lib/dot">GraphViz</a>, <a href="https://observablehq.com/framework/lib/tex">TeX</a>, or <a href="https://observablehq.com/framework/lib/duckdb">DuckDB</a>.
  </div>
  <div class="card">
    Ask for help, or share your work or ideas, on our <a href="https://github.com/observablehq/framework/discussions">GitHub discussions</a>.
  </div>
  <div class="card">
    Visit <a href="https://github.com/observablehq/framework">Framework on GitHub</a> and give us a star. Or file an issue if you’ve found a bug!
  </div>
</div>

<style>

.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: var(--sans-serif);
  margin: 4rem 0 8rem;
  text-wrap: balance;
  text-align: center;
}

.hero h1 {
  margin: 1rem 0;
  padding: 1rem 0;
  max-width: none;
  font-size: 14vw;
  font-weight: 900;
  line-height: 1;
  background: linear-gradient(30deg, var(--theme-foreground-focus), currentColor);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero h2 {
  margin: 0;
  max-width: 34em;
  font-size: 20px;
  font-style: initial;
  font-weight: 500;
  line-height: 1.5;
  color: var(--theme-foreground-muted);
}

@media (min-width: 640px) {
  .hero h1 {
    font-size: 90px;
  }
}

blockquote, ol, ul {
    max-width: 1200px;
}
.card.big {
    font-size:15pt;
    text-align:center;
}

</style>
