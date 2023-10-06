

<script setup lang="ts">
import { useTresContext } from '@tresjs/core'
const context = useTresContext()


const groupRef = ref()
const { onLoop } = useRenderLoop()

onLoop( () => {
    if ( groupRef.value ) {
        groupRef.value.rotation.y += 0.01
    }
} )
</script>
<template>
    <TresGroup ref="groupRef" :position="[2, 0, 0]">
        <TresMesh>
            <TresBoxGeometry />
            <TresMeshBasicMaterial />
        </TresMesh>
        <TresMesh :position="[-2, 0, 0]">
            <TresSphereGeometry />
            <TresMeshBasicMaterial />
        </TresMesh>
    </TresGroup>
</template>