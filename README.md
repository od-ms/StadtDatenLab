# StadtDatenLab Muenster

Vision:
* Hier soll ein Internetangebot entstehen, das Daten aus der Stadtverwaltung Münster visualisiert. Es soll möglich sein, Visualisierungen in Form von Diagramme, Karten und Graphen abzurufen. Besucher*innen sollen städtische Daten erkunden, anschauen und prüfen können. Ein niederschwellig zugänglicher Faktencheck soll ermöglicht werden.

---

## Ideen zur Umsetzung der Datenvisualisierungen

DatenDateien sollten Frictionless DataPackage-Beschreibungen erhalten:
* https://datapackage.org/standard/data-package/ -

Datensätze automatisch mit Github Actions einchecken:
* Beispiele hier: https://github.com/datasets

Ideen für Projektnamen:
* StadtDatenHub, DatenChecker, FaktenFinder, DatenNavigator, StadtDatenLab, DatenKompass, DatenExplorer, DatenRadar, DatenLabor, OpenVis, OpenDataWelt, InfoAtlas, DatenBuddy

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

---


This is an [Observable Framework](https://observablehq.com/framework/) app. To install the required dependencies, run:

```
npm install
```

Then, to start the local preview server, run:

```
npm run dev
```

Then visit <http://localhost:3000> to preview your app.

For more, see <https://observablehq.com/framework/getting-started>.

## Project structure

A typical Framework project looks like this:

```ini
.
├─ src
│  ├─ components
│  │  └─ timeline.js           # an importable module
│  ├─ data
│  │  ├─ launches.csv.js       # a data loader
│  │  └─ events.json           # a static data file
│  ├─ example-dashboard.md     # a page
│  ├─ example-report.md        # another page
│  └─ index.md                 # the home page
├─ .gitignore
├─ observablehq.config.js      # the app config file
├─ package.json
└─ README.md
```

**`src`** - This is the “source root” — where your source files live. Pages go here. Each page is a Markdown file. Observable Framework uses [file-based routing](https://observablehq.com/framework/project-structure#routing), which means that the name of the file controls where the page is served. You can create as many pages as you like. Use folders to organize your pages.

**`src/index.md`** - This is the home page for your app. You can have as many additional pages as you’d like, but you should always have a home page, too.

**`src/data`** - You can put [data loaders](https://observablehq.com/framework/data-loaders) or static data files anywhere in your source root, but we recommend putting them here.

**`src/components`** - You can put shared [JavaScript modules](https://observablehq.com/framework/imports) anywhere in your source root, but we recommend putting them here. This helps you pull code out of Markdown files and into JavaScript modules, making it easier to reuse code across pages, write tests and run linters, and even share code with vanilla web applications.

**`observablehq.config.js`** - This is the [app configuration](https://observablehq.com/framework/config) file, such as the pages and sections in the sidebar navigation, and the app’s title.

## Command reference

| Command           | Description                                              |
| ----------------- | -------------------------------------------------------- |
| `npm install`            | Install or reinstall dependencies                        |
| `npm run dev`        | Start local preview server                               |
| `npm run build`      | Build your static site, generating `./dist`              |
| `npm run deploy`     | Deploy your app to Observable                            |
| `npm run clean`      | Clear the local data loader cache                        |
| `npm run observable` | Run commands like `observable help`                      |
