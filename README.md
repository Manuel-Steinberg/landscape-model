# Open Source APM Landscape
Model for the open-source application performance management (APM) landscape presented on the [OpenAPM](https://openapm.io/landscape) website.
The landscape illustrates the possibilities of combining different open-source tools to build tailored APM solutions.

## Build
Building means combining all model files into one JSON file. The easiest way to do this is to execute the following command:
```
$ npm install
$ npm run-script build
```
The output file will be written to `build/model.json`.

## Local Visualization
An interactive graph visualization is included in `landscape.html`. It uses [Cytoscape.js](https://js.cytoscape.org) to render components as a force-directed graph with data-flow edges.

Because the page fetches `build/model.json`, it must be served over HTTP rather than opened as a local file. Start a server from the repo root:

```
$ npx serve .
```

`serve` will pick an available port and print the URL — open the printed URL and append `/landscape.html`. Stop the server with `Ctrl+C`.

Features:
- Nodes color-coded by category (Agent, Collector, Storage, Alerting, etc.)
- Category filter buttons and a search box in the toolbar
- Click any node to see its description, links, and connections in a side panel
- Click connections in the panel to navigate to related components
- Re-layout button to re-run the physics layout

Run the build step first if `build/model.json` is not present or out of date.

## Contributing
Read [this notes](https://github.com/openapm/landscape-model/blob/master/CONTRIBUTE.md) on how to contribute to the OpenAPM landscape!