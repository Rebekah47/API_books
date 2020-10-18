<template lang="html">
  <div>
      <ul>
        <race-item v-for="(race, index) in races" :race="race" :key="index"></race-item>   
        <select v-on:change="handleChange" id="race-selected" v-model="selectedRace">
        <option disabled value="">Select a Species</option>
        <option v-for="(race, index) in races" :race="race" :value="race" :key="index">{{race.name}}</option>
        </select>
    </ul>
    </div>
</template>

<script>
import {eventBus} from '../main.js'
import RaceItem from './RaceItem.vue'
export default {
    name:'race-list',
    data(){
        return{
            selectedRace:null
        }
    },
    props: ['races'],
    components: {
        "race-item": RaceItem
    },
    methods: {
        handleChange(){
            eventBus.$emit('race-selected', this.selectedRace)
        }
    }
}
</script>

<style>

</style>