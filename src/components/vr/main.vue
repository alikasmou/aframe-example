<script lang="ts" setup>
import { ref, onMounted } from "vue";
const aframeBaseScripts = [
  { src: "https://aframe.io/releases/1.3.0/aframe.min.js" },
];

onMounted(() => {
  aframeBaseScripts.map((item) => {
    let script = document.createElement("script");
    script.setAttribute("src", item.src);
    // document.head.appendChild(script);
  });
});
</script>
<template>
  <div>
    <slot name="vr-frame"></slot>
  </div>
</template>
