<script setup lang="ts">
import { onMounted } from "vue";
import VR from "@/components/vr/main.vue";

// import { FBXLoader } from "https://cdn.jsdelivr.net/npm/three@0.118.1/examples/jsm/loaders/FBXLoader.js";

const plugins = [
  { src: "/plugins/vr/intersection-spawn.js" },
  { src: "/plugins/vr/random-color.js" },
  { src: "/plugins/vr/snap.js" },
];
onMounted(() => {
  plugins.map((item) => {
    let el = document.createElement("script");
    el.setAttribute("src", item.src);
    document.head.appendChild(el);
  });
});
</script>
<template>
  <VR>
    <template #vr-frame>
      <!-- <a-scene> -->
      <!-- <a-assets>
          <a-asset-item
            id="car"
            src="/assets/vr/boy/boy.gltf"
            crossOrigin="anonymous"
          ></a-asset-item>
        </a-assets>
        <a-gltf-model src="#car" position="0 0 0"></a-gltf-model>
        <a-entity
          light="color: #FFFFFF; intensity: 0.6"
          position="1 1 0"
        ></a-entity>
        <a-entity
          id="ground"
          geometry="primitive: box; width: 20; height: 0.01; depth: 20"
          material="color: #eee;"
          position="0 0 -4"
        ></a-entity>
        <a-entity
          light="type: directional; color: #FFF; intensity: 0.6"
          position="-0.5 1 1"
        ></a-entity> -->

      <!-- <a-entity fbx-model="src: url(assets/fbx/Son.fbx);"> </a-entity> -->
      <!-- <a-asset-item id="objectModel" src="/assets/fbx/Son.fbx"></a-asset-item>
        <a-entity
          gltf-model="#objectModel"
          position="0 0 0"
          scale="0.01 0.01 0.01"
          animation-mixer
        ></a-entity>
      </a-scene> -->
      <a-scene>
        <a-assets>
          <a-asset-item
            id="car"
            src="/assets/Haya.gltf"
            crossOrigin="anonymous"
          ></a-asset-item>
        </a-assets>
        <a-gltf-model src="#car" position="0 0 0"></a-gltf-model>
        <a-entity
          light="color: #FFFFFF; intensity: 0.6"
          position="1 1 0"
        ></a-entity>
        <a-entity
          id="ground"
          geometry="primitive: box; width: 20; height: 0.01; depth: 20"
          material="color: #eee;"
          position="0 0 -4"
        ></a-entity>
        <a-entity
          light="type: directional; color: #FFF; intensity: 0.6"
          position="-0.5 1 1"
        ></a-entity>
        <a-entity
          id="leftHand"
          hand-controls="hand: left; handModelStyle: lowPoly; color: #ffcccc"
        ></a-entity>
        <a-entity
          id="rightHand"
          hand-controls="hand: right; handModelStyle: lowPoly; color: #ffcccc"
        ></a-entity>
      </a-scene>
    </template>
  </VR>
</template>
