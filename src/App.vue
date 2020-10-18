<template lang='html'>
  <div id="app">
    <h1>The Creatures of  and Dragons</h1>
    <div>
    <race-list :races='races'></race-list>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import RaceList from './components/RaceList.vue'
import RaceItem from './components/RaceItem.vue'
import RaceDetails from './components/RaceDetails.vue'

export default {
  name: 'App',
  data(){
    return{
      races: [],
      selectedRace: null,
    }
  },
  mounted(){
    console.log('mounted called')
    fetch('https://www.dnd5eapi.co/api/races')
    .then(res => res.json())
    .then(races => console.log(races))

    eventBus.$on('race-selected', (race) => {
      this.selectedRace = race
    })
  },
  components: {
    'race-list': RaceList,
    'race-details': RaceDetails
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
