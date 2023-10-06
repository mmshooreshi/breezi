<script setup >

import { useRenderLoop } from '@tresjs/core';

const boxRef = ref(null);

const { onLoop } = useRenderLoop();

onLoop(({ delta, elapsed }) => {
  if (boxRef.value) {
    boxRef.value.rotation.y += delta * 0.1;
    boxRef.value.rotation.z = elapsed * 0.2;

  }
});
</script>

<template>
  <TresCanvas clear-color="#000" shadows alpha window-size>
    <OrbitControls />
    <TresAmbientLight :intensity="1" />
    <TresAmbientLight :position="[0, -4, -2]" :intensity="1" />

    <TresAmbientLight :position="[0, -4, 2]" :intensity="1" />
    <TresDirectionalLight :intensity="1" :position="[0, 8, -8]" />
    <TresDirectionalLight :position="[0, -4, -40]" />
    <TresPerspectiveCamera :position="[-5, 2, 5]" :fov="45" :aspect="1" :near="0.1" :far="1000" />
    <TresMesh ref="boxRef" :scale="1" cast-shadow>
      <TresBoxGeometry :args="[2, 2, 2, 10]" />
      <MeshGlassMaterial />
    </TresMesh>
    <TresGridHelper :args="[100, 100]" />


  </TresCanvas>
</template>
