
<p align="center"><img src="images/maplibre_layerhub_title.svg"  /></p>

<!-- <h1 align='center'>MapLibreLayerHub</h1> -->

<p align="center">
<a href=""><img src="https://img.shields.io/badge/version-1.0-yellow.svg" /></a>
<a href=""><img src="https://img.shields.io/badge/author-Jinghao%20Hu-orange.svg" /></a>
<a href=""><img src="https://img.shields.io/badge/language-TypeScript-blue.svg" /></a>
<a href="http://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-green.svg" /></a>
</p>

> **MapLibreLayerHub**: 基于 Maplibre 开发的图层管理控件，完美结合 layui 的 layer、bootstrap-slider 和 ztree。

---

## 目录

- [背景](#背景)
- [功能](#功能)
- [安装](#安装)
- [使用](#使用)
  - [图层管理](#图层管理)
- [API](#api)
- [文档](#文档)
- [作者](#作者)
- [贡献](#贡献)
- [许可证](#许可证)

---

## 背景

**MapLibreLayerHub** 旨在简化 Maplibre 地图中的图层集成与管理。通过结合 layui 的模态框、bootstrap 滑块和 ztree，本包提供了全面的图层管理功能，帮助开发者轻松构建丰富的互动地图应用。

---

## 功能

- **全面的图层管理**：轻松切换、组织和自定义图层显示。
- **可自定义控件**：支持 layui 的模态框、bootstrap 滑块和 ztree，为用户提供灵活的界面体验。
- **高效扩展**：高效处理大量图层，性能表现优越。

---

## 安装

请确保您已经安装了 [npm](https://npmjs.com) 和 [node](http://nodejs.org)。

```sh
$ npm install maplibre-layerhub --save
```

---

## 使用

在项目中添加 MapLibreLayerHub 并初始化它以开始管理您的地图图层。

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
    layerOptions: { /* 图层自定义设置 */ },
});
```

---

### 图层管理

要管理和切换特定图层：

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

layerHub.toggleLayer('my-layer', false); // 隐藏图层
```

---

## API

- **图层控制**

| 函数                | 描述               |
|---------------------|--------------------|
| `addLayer(options)` | 向地图添加新图层   |
| `toggleLayer(id)`   | 切换图层的可见性   |
| `removeLayer(id)`   | 从地图移除图层     |

- **滑块控制**

| 函数                 | 描述                              |
|----------------------|-----------------------------------|
| `setOpacity(id, value)` | 通过 bootstrap 滑块设置图层透明度  |
| `setZIndex(id, index)`  | 调整图层的 z-index              |

- **树管理**

| 函数                  | 描述                            |
|-----------------------|-------------------------------|
| `addTreeNode(data)`   | 向图层管理树添加节点          |
| `removeTreeNode(id)`  | 从图层树中移除节点            |

---

## 文档
- [图层配置](docs/layer-config.md)
- [控制选项](docs/control-options.md)
- [集成指南](docs/integration.md)

---

## 作者

由 [@JinghaoHu](https://github.com/hujinghaoabcd) 创建。

---

## 贡献

欢迎社区成员参与贡献！如有兴趣，请提交 [pull request](https://github.com/hujinghaoabcd/MapLibreLayerHub/pulls)。

---

## 许可证

[MIT © 2024 hujinghao | 中国科学院大学 (UCAS)](./LICENSE)