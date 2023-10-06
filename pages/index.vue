<script setup lang="ts">
import { shallowRef } from 'vue'
import { TresCanvas, useRenderLoop } from '@tresjs/core'
import { Stars, OrbitControls } from '@tresjs/cientos'

// const yRotation = shallowRef( 0 )
// useRenderLoop().onLoop( ( { delta } ) => {
//     yRotation.value += 0.02 * delta
// } )


</script>

<template>
    <TresCanvas window-size clear-color="#333">
        <TresPerspectiveCamera :position="[0, 2, 5]" />
        <!-- <Stars :rotation="[0, yRotation, 0]" :radius="5" :depth="3" :count="5000" :size="0.02" :size-attenuation="true" /> -->
        <TresGridHelper :args="[8, 8]" />
        <OrbitControls />
    </TresCanvas>
</template>