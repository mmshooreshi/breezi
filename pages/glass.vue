<script setup lang="ts">
import { TresCanvas } from '@tresjs/core'
import { MapControls, Sphere, MeshGlassMaterial, OrbitControls } from '@tresjs/cientos'


</script>

<template>
    <TresCanvas window-size shadow clear-color="#232E3F">

        <MapControls />



        <Box :args="[1, 1, 1]" color="orange" />

        // Box with a custom material transformations
        <Box ref="boxRef" :args="[1, 1, 1]" :position="[0, 4, 0]">
            <TresMeshToonMaterial color="orange" />
        </Box>




        <TresGridHelper color="red" :args="[10, 10]" />


        <Sphere :position="[0, 3, 0]" :scale="0.3">
            <!-- <TresMeshNormalMaterial /> -->
            <MeshGlassMaterial />
        </Sphere>
        <TresAmbientLight :intensity="1" />

        <TresAmbientLight :position="[0, -40, -2]" :intensity="1" />
        <TresDirectionalLight :intensity="1" :position="[0, 8, -8]" />
        <TresDirectionalLight :position="[0, -4, -40]" />

        <OrbitControls />


    </TresCanvas>
</template>