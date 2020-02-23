<template lang="html">
  <div class="">
    <h1>How much CO2 does the UK spew?</h1>
    <generation :generationData='generationData'/>
    <region-list :regionListArray='regionListArray'/>
    <region-detail :selectedRegion='selectedRegion'/>
  </div>

</template>

<script>
import {eventBus} from './main.js';
import Generation from './components/Generation.vue';
import RegionList from './components/RegionList.vue';
import RegionItem from './components/RegionItem.vue';
import RegionDetail from './components/RegionDetail.vue';


export default {
  name: 'app',
  data(){
    return {
      generationData: [],
      regionListArray: [],
      selectedRegion: null
    }
  },
  components: {
    'generation': Generation,
    'region-list': RegionList,
    'region-item': RegionItem,
    'region-detail': RegionDetail
  },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/intensity/factors')
    .then(res => res.json())
    .then(generationData => this.generationData = generationData)
    fetch('https://api.carbonintensity.org.uk/regional')
    .then(res => res.json())
    .then(regionListArray => this.regionListArray = regionListArray)

    eventBus.$on("region-selected", (region) => this.selectedRegion = region)
  }
}
</script>

<style lang="css" scoped>
</style>
