<script setup lang="ts">
import { OrbitControls, Smoke, useGLTF, Precipitation } from '@tresjs/cientos'
import { BasicShadowMap, sRGBEncoding, NoToneMapping, Shape } from 'three'
console.log( 'jaime ~ Precipitation:', Precipitation )
const gl = {
    shadows: true,
    alpha: false,
    shadowMapType: BasicShadowMap,
    outputEncoding: sRGBEncoding,
    toneMapping: NoToneMapping,
}
const { scene } = await useGLTF( 'https://raw.githubusercontent.com/Tresjs/assets/main/models/gltf/blender-cube.glb' )
</script>
<template>
    <TresCanvas window-size v-bind="gl">

        <TresPerspectiveCamera :position="[0, 6, 12]" />
        <!-- <Suspense>
            <Smoke :position="[-4, -2, 0]" :segments="8" />
        </Suspense>
        <Suspense>
            <Smoke :position="[-4, 2, 0]" :segments="8" />
        </Suspense>
        <Suspense>
            <Smoke :segments="8" color="#c4c4c4" />
        </Suspense>
        <Suspense>
            <Smoke :position="[4, -2, 0]" :segments="8" />
        </Suspense>
        <Suspense>
            <Smoke :position="[4, 2, 0]" :segments="8" />
        </Suspense> -->
        <!-- <primitive :object="scene" /> -->
        <!-- <Precipitation :area="[15, 15, 15]" :size="0.1" :count="500" :speed="2" :randomness="0" /> -->
        <TresGridHelper :size="10" :divisions="10" :position-y="-1" />
        <TresMesh class="group" :position="[0, 0, 0]">
            <TresBoxGeometry :args="[2, 2, 2]" />
            <MeshGlassMaterial />
            <TresMeshNormalMaterial :opacity="0.5" class="hover:hidden visible " />

        </TresMesh>
        <TresAmbientLight :intensity="1" />

        <TresDirectionalLight :intensity="1" :position="[2, 2, 2]" />


        <OrbitControls />
    </TresCanvas>
</template>