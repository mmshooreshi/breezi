<script setup>
import { OrbitControls } from '@tresjs/cientos'

</script>


<template>
    <TresCanvas window-size shadows alpha>
        <TresPerspectiveCamera :args="[45, 1, 0.1, 1000]" />
        <OrbitControls />
    </TresCanvas>
</template>