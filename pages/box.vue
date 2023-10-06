<template>
    <TresCanvas window-size clear-color="#82dbc5">
        <!-- <TresMesh>
            <TresBoxGeometry :args="[2, 1, 1]" />
            <TresMeshBasicMaterial color="yellow" />
        </TresMesh> -->

        <TresMesh :position="[0, 1, 2]">
            <TresBoxGeometry :args="[2, 1, 1]" />
            <TresMeshBasicMaterial color="yellow" />
        </TresMesh>




        <TresCanvas clear-color="#333">
            <TresPerspectiveCamera :position="[0, 2, 5]" />
            <Stars :rotation="[0, yRotation, 0]" :radius="50" :depth="50" :count="5000" :size="0.3"
                :size-attenuation="true" />
            <TresGridHelper :args="[4, 4]" />
            <OrbitControls />
        </TresCanvas>


    </TresCanvas>
</template>


<script setup>

// const geometry = new THREE.BoxGeometry(2, 1, 1) // [width, height, depth]


// const material = new THREE.MeshBasicMaterial()
// material.color = new Color('yellow')

</script>