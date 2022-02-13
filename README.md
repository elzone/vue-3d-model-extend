# vue-3d-model-extend


# <a src="https://github.com/hujiulong/vue-3d-model" alt="github link">a fork from vue-3d-model</a>


vue.js 3D model viewer component, based on threejs, inspired by [model-tag](https://github.com/mrdoob/model-tag)

## Install
using npm
```
npm install @elzone/vue-3d-model-extend --save
```
Or using script tag for global use
```html
<script src="https://unpkg.com/@elzone/vue-3d-model-extend/dist/vue-3d-model-extend.umd.js"></script>
```

Or Download <a href="https://unpkg.com/@elzone/vue-3d-model-extend/dist/vue-3d-model-extend.umd.js">@elzone/vue-3d-model-extend.js</a> and include it in your html

## Usage

```vue
<template>
  <model-obj src="example/models/obj/LeePerrySmith.obj"></model-obj>
</template>
<script>
import { ModelObj } from 'vue-3d-model-extend';
export default {
  components: { ModelObj }
}
</script>
```
Or
```vue
<!DOCTYPE html>
<html>
<head>
 <meta charset="UTF-8"></head>
<body>
  <div id="app">
    <model-obj src="example/models/obj/LeePerrySmith.obj"></model-obj>
  </div>
<script src="vue.js"></script>
<script src="vue-3d-model-extend.umd.js"></script>
<script>
  new Vue({ el: '#app' });
</script>
</body>
```

## Documents

### props
| prop            | type          | default              |  example                                   |
| --------------- |---------------|----------------------|--------------------------------------------|  
| src             | string        | -                    | './exapmle.obj'                            |
| width           | number        | -                    | 300                                        |
| height          | number        | -                    | 300                                        |
| position        | object        | { x: 0, y: 0, z: 0 } | { x: 100, y: 20, z: -10 }                  |
| rotation        | object        | { x: 0, y: 0, z: 0 } | { x: Math.PI / 2, y: 0, z: - Math.PI / 4 } |
| cameraPosition  | object        | { x: 0, y: 0, z: 0 } | { x: 1, y: 2, z: -3 } |
| cameraRotation  | object        | { x: 0, y: 0, z: 0 } | { x: 3, y: 2, z: -1 } |
| scale           | object        | { x: 1, y: 1, z: 1 } | { x: 2, y: 2, z: 3 }                       |
| lights          | array         | -                    |                                            |
| backgroundColor | number/string | 0xffffff             | 0xffffff/'#f00'/'rgb(255,255,255)'         |
| backgroundAlpha | number        | 1                    | 0.5                                        |
| controlsOptions | object        | -                    | see [OrbitControls Properties](https://threejs.org/docs/#examples/en/controls/OrbitControls) |
| crossOrigin     | string        | anonymous            | anonymous/use-credentials                  |
| requestHeader   | object        | -                    | { 'Authorization: Bearer token' }          |
| outputEncoding     | number       | THREE.LinearEncoding                | see [WebGLRenderer OutputEncoding](https://threejs.org/docs/index.html#api/en/renderers/WebGLRenderer.outputEncoding)                                 |
| glOptions       | object        | { antialias: true, alpha: true }  | see [WebGLRenderer Parameters](https://threejs.org/docs/index.html#api/en/renderers/WebGLRenderer) |

### events

| event         |
|---------------|
| on-mousedown  |
| on-mousemove  |
| on-mouseup    |
| on-mousewheel |
| on-click      |
| on-load       |
| on-progress   |
| on-error      |

## Model Format Support
| model format  | component tag     |
| ------------- |-------------------|
| obj           | \<model-obj>      |
| json          | \<model-three>    |
| stl           | \<model-stl>      |
| dae           | \<model-collada>  |
| ply           | \<model-ply>      |
| fbx           | \<model-fbx>      |
| gltf(2.0)     | \<model-gltf>     |

## Browser Support
Modern browsers and IE 11.

You can click on [this](http://caniuse.com/#search=webgl) for more information. 

## TODO List
* Support for more model formats
* Animation
* Post-processing

## LICENSE
MIT
