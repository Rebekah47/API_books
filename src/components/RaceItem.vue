<template lang="html">
<li>{{race.name}}</li>
</template>

<script>
import {eventBus} from '../main.js'
export default {
    name: 'race-item',
    props: ['race']
}
</script>

<style>

</style>