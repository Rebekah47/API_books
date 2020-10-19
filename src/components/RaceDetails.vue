<template lang="html">
    <div v-if="race">
        <h2>{{race.name}}</h2>
        <p>Alignment:{{race.alignment}}</p>
        <p>{{race.name}}'s Language Proficiency: {{race.language_desc}}</p>
    </div>
</template>

<script>
export default {
    name: "race-details",
    props: ['race'] ['raceSelected']
}
</script>

<style>

</style>