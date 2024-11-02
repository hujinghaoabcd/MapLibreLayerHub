<p align="center"><img src="https://sdasddas.oss-cn-hangzhou.aliyuncs.com/keyan/202304082356547.png" /></p>

<h1 align='center'>MapLibreLayerHub</h1>

<p align="center">
<a href=""><img src="https://img.shields.io/badge/version-1.0-yellow.svg" /></a>
<a href=""><img src="https://img.shields.io/badge/author-Jinghao%20Hu-orange.svg" /></a>
<a href=""><img src="https://img.shields.io/badge/language-TypeScript-blue.svg" /></a>
<a href="http://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-green.svg" /></a>
</p>

> **MapLibreLayerHub**: An efficient layer management control built on Maplibre, with seamless integration of layui's layer, bootstrap-slider, and ztree.

English | [中文](#中文)

---

## Table of Contents

- [Background](#background)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Layer Management](#layer-management)
- [API](#api)
- [Documentation](#documentation)
- [Authors](#authors)
- [Contributing](#contributing)
- [License](#license)

---

## Background

**MapLibreLayerHub** is designed to streamline the integration and management of layers within Maplibre-based maps. Using the flexibility of layui's layer, bootstrap-slider, and ztree, this package offers comprehensive controls for layer visibility, hierarchy, and interaction, making it easy for developers to build rich, interactive map applications.

---

## Features

- **Comprehensive Layer Management**: Easily toggle, organize, and customize layer display.
- **Customizable Controls**: Built-in support for layui's modal layers, bootstrap sliders, and ztree for a flexible UI experience.
- **Efficient and Scalable**: Handles large sets of layers with minimal performance overhead.
  
---

## Installation

Make sure to have [npm](https://npmjs.com) and [node](http://nodejs.org) installed.

```sh
$ npm install maplibre-layerhub --save
```

---

## Usage

Add MapLibreLayerHub to your project and initialize it to start managing your map layers.

```javascript
import MapLibreLayerHub from 'maplibre-layerhub';
import maplibre from 'maplibre-gl';

const map = new maplibre.Map({
    container: 'map',
    style: 'https://demotiles.maplibre.org/style.json',
    center: [0, 0],
    zoom: 2
});

const layerHub = new MapLibreLayerHub(map, {
    layerOptions: { /* Custom settings for layers */ },
});
```

---

### Layer Management

To manage and toggle specific layers:

```javascript
layerHub.addLayer({
    id: 'my-layer',
    type: 'circle',
    source: {
        type: 'geojson',
        data: 'path/to/data.geojson'
    },
    layout: {
        visibility: 'visible'
    }
});

layerHub.toggleLayer('my-layer', false); // Hide the layer
```

---

## API

- **Layer Controls**

| Function            | Description                           |
|---------------------|---------------------------------------|
| `addLayer(options)` | Adds a new layer to the map.          |
| `toggleLayer(id)`   | Toggles the visibility of a layer.    |
| `removeLayer(id)`   | Removes a layer from the map.         |

- **Slider Controls**

| Function                   | Description                                |
|----------------------------|--------------------------------------------|
| `setOpacity(id, value)`    | Sets layer opacity via bootstrap slider.   |
| `setZIndex(id, index)`     | Adjusts the z-index of a specific layer.   |

- **Tree Management**

| Function              | Description                            |
|-----------------------|----------------------------------------|
| `addTreeNode(data)`   | Adds a node to the layer management tree. |
| `removeTreeNode(id)`  | Removes a node from the layer tree.       |

---

## Documentation
- [Layer Configuration](docs/layer-config.md)
- [Control Options](docs/control-options.md)
- [Integration Guide](docs/integration.md)

---

## Authors

Created by [@JinghaoHu](https://github.com/hujinghaoabcd).

---

## Contributing

We welcome contributions from the community! If you'd like to contribute, please open a [pull request](https://github.com/hujinghaoabcd/MapLibreLayerHub/pulls).

---

## License

[MIT © 2024 hujinghao | 中国科学院大学 (UCAS)](./LICENSE)


