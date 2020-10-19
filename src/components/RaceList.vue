<template lang="html">
  <div>
      <ul>   
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
            selectedRace:null,
            detailSelected: [],
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
    },
    mounted(){
        fetch('/this.selectedRace.url', {referrer: "https://www.dnd5eapi.co"})
        console.log(detailSelected)
        .then(res => res.json())
        .then(detailSelected => this.detailSelected = detailSelected)
    }
}
</script>

<style>

</style>