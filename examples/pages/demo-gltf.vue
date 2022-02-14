<template>
  <demo-block :vue-code="code" :html-code="htmlCode">
    <template slot="preview">
      <model-gltf
        :backgroundAlpha="0"
        @on-load="onLoad"
        @on-wheel="onWheel"
        :camera-quaternion="cameraQuaternion"
        :camera-position="cameraPosition"
        :camera-rotation="cameraRotation"
        src="static/models/gltf/Duck/glTF/Duck.gltf"
      ></model-gltf>
      <div class="example-loading" v-show="loading"></div>
    </template>
  </demo-block>
</template>

<script>
import DemoBlock from '../components/demo-block.vue';
import ModelGltf from '../../src/model-gltf.vue';

const code = `

<template>
    <model-gltf src="static/models/gltf/Duck/glTF/Duck.gltf"></model-gltf>
</template>

<script>
    import { ModelGltf } from 'vue-3d-model-extend'

    export default {
        components: {
            ModelGltf
        }
    }
<\/script>

`;

const htmlCode = `
<body>
    <div id="app">
        <model-gltf 
            src="static/models/gltf/Duck/glTF/Duck.gltf"
            @on-mousemove="onMouseMove">
        </model-gltf>
    </div>
    #scripts#
    <script>
        new Vue({
            el: '#app'
        })
    <\/script>
</body>
`;

export default {
  name: 'demo-gltf',
  data() {
    return {
      code,
      htmlCode,
      loading: true,
      cameraQuaternion: {
        x: 0,
        y: 0,
        z: 0,
        w: 0,
      },
      cameraRotation: {
        x: 0,
        y: 0,
        z: 0,
      },
      cameraPosition: {
        x: 0,
        y: 0,
        z: 0,
      },
    };
  },
  methods: {
    onLoad() {
      this.loading = false;
      this.cameraQuaternion = {
        x: 0.09,
        y: 0.88,
        z: 0.21,
        w: -0.38,
      };
      this.cameraRotation = {
        x: -2.47,
        y: -0.72,
        z: -2.65,
      };
      this.cameraPosition = {
        x: -1041,
        y: 730,
        z: -925,
      };
    },
    onWheel(event) {
      console.log(event);
    },
  },
  components: {
    ModelGltf,
    DemoBlock,
  },
};
</script>
